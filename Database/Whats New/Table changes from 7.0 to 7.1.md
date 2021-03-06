---
uid: Tablechangesfrom7.0to7.1
title: Table changes from 7.0 to 7.1
---

**New tables**

[outgoing\_message](../Tables/OUTGOING_MESSAGE.md) (407) Delivery of outgoing messages to messageplugins, updated with status asynchroneously

|                       |              |                                    |
|-----------------------|--------------|------------------------------------|
| id                    | int          | The primary key (auto-incremented) |
| session\_key          | varchar(256) | Session key used for threading.    |
| external\_message\_id | varchar(256) | Session key used for threading.    |
| status                | int          | Current status of outgoing message |
| status\_description   | varchar(256) | Description of current status      |
| plugin                | varchar(256) | Name of plugin                     |
| reg                   | DateTime     | Registered when                    |
| reg\_id               | int          | Registered by whom                 |
| updated               | DateTime     | Last updated when                  |
| update\_id            | int          | Last updated by whom               |

**New fields on existing tables**

[Appointment](../Tables/APPOINTMENT.md)

|             |        |                                                                                                                   |
|-------------|--------|-------------------------------------------------------------------------------------------------------------------|
| isMilestone | ushort | Is this appointment a project milestone? In 7.1 this can only be set via the Project Guide, and not changed later |

[Project](../Tables/PROJECT.md) 

|                   |          |                                                                                  |
|-------------------|----------|----------------------------------------------------------------------------------|
| endDate           | DateTime | Planned end date for project, inherited from project type, and editable later    |
| nextMilestoneDate | DateTime | Calculated date, reflects date of closest non-complete future milestone activity |
| nmdAppointmentId  | int      | ID of appointment that "caused" the nextMilestoneDate, can be 0                  |

 

[ProjType](../Tables/PROJTYPE.md) 

|                 |       |                                                                                                                   |
|-----------------|-------|-------------------------------------------------------------------------------------------------------------------|
| projectDuration | int   | Is this appointment a project milestone? In 7.1 this can only be set via the Project Guide, and not changed later |
| durationUnit    | short | Units for the duration                                                                                            |
| hasGuide        | short | Does this project type have a guide attached                                                                      |
| isAutoAdvance   | short | Does the project status advance automatically, when the last guided activity in a status is completed?            |

 

[SuggestedAppointment](../Tables/SUGGESTEDAPPOINTMENT.md)

|                |        |                                                               |
|----------------|--------|---------------------------------------------------------------|
| isMilestone    | ushort | Is this kind of appointment a milestone in a project          |
| assignToMember | short  | Should generated appointment be assigned to a project member? |

 

[SaleType](../Tables/SALETYPE.md) 

|                 |       |                                   |
|-----------------|-------|-----------------------------------|
| hasStakeholders | short | this sale type have stakeholders? |

 

[ticket](../Tables/TICKET.md)

|        |       |                                   |
|--------|-------|-----------------------------------|
| origin | short | What is the origin of this ticket |

 

[extra\_menus](../Tables/EXTRA_MENUS.md)

|               |       |                                             |
|---------------|-------|---------------------------------------------|
| base\_program | short | Base program used in url (ticket, rms, ...) |
| extra\_table  | int   | ExtraTable that the menu is connected to    |

 

[s\_link](../Tables/S_LINK.md)

|                                   |                |                                                                                                                                                       |
|-----------------------------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|
| action\_flags                     | short          | Bitmask defining what action should be taken                                                                                                          |
| add\_contact\_interest            | int            | Contact interest to add to recipient person                                                                                                           |
| remove\_contact\_interest         | int            | Person interest to remove from recipient person                                                                                                       |
| add\_person\_interest             | int            | Person interest to add to recipient person                                                                                                            |
| remove\_person\_interest          | int            | Person interest to remove from recipient person                                                                                                       |
| add\_contact\_selection           | int            | Static contact selection to add person to                                                                                                             |
| remove\_contact\_selection        | int            | Static contact selection to remove person from                                                                                                        |
| add\_project                      | int            | Project to add person to, as member                                                                                                                   |
| remove\_project                   | int            | Project to remove person from, as member                                                                                                              |
| task\_text                        | varchar(2048)  | Text of task to be created                                                                                                                            |
| task\_idx                         | int            | Task type of new task                                                                                                                                 |
| task\_flags                       | short          | Flags that control how the task is created                                                                                                            |
| task\_associate\_id               | int            | Associate whose diary should receive the task or assignment (unless AssignToOurContact is specified)                                                  |
| task\_creating\_associate\_id     | int            | Associate who should stand as creator of task; also works as fallback if an assigned task is rejected. Usually the associate who ordered the shipment |
| task\_project                     | int            | Project to connect task to, can be 0                                                                                                                  |
| task\_start                       | DateTime       | Start time of task, unless UseNextAvailableTime is specified                                                                                          |
| task\_duration                    | int            | Task duration in minutes                                                                                                                              |

[s\_shipment\_addr](../Tables/S_SHIPMENT_ADDR.md)

|               |          |                                                                     |
|---------------|----------|---------------------------------------------------------------------|
| ticket\_id    | int      | Id of the ticket if this entry is created by a ticketSelection list |
| status        | short    | Status for sending to this particular recipient                     |
| contact\_id   | int      | Id of contact bound to shipment address                             |
| sending\_time | DateTime | Estimated or actual sent time (depends on status)                   |

[s\_list\_shipment](../Tables/S_LIST_SHIPMENT.md)

|        |       |                         |
|--------|-------|-------------------------|
| status | short | Status of shipment list |

 

[inbox](../Tables/INBOX.md)

|        |              |                                        |
|--------|--------------|----------------------------------------|
| plugin | varchar(256) | Name of plugin that created this inbox |
| format | varchar(256) | Format of the inbox entry              |

[sms](../Tables/SMS.md)

|                       |              |                                                                                            |
|-----------------------|--------------|--------------------------------------------------------------------------------------------|
| session\_key          | varchar(256) | The reference used for identifying a session, like in-reply-to and message-id              |
| outgoing\_message\_id | int          | Reference to the outgoing message entry created by netserver for sending and status update |