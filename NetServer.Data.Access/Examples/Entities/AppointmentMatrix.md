<properties date="2016-05-11"
/>

The AppointmentMatrix is used to manage complex appointments: invitations and recurrences.

```
    using SuperOffice.CRM.Entities;
    
    // Let the participant accept this one
    using (SoSession.Authenticate("tje3", "tje3"))
    {
        int appointmentId = 123;
        Appointment appointment =
Appointment.GetFromIdxAppointmentId( appointmentId );
        AppointmentMatrix matrix = new
AppointmentMatrix(appointment,
RecurrenceUpdateMode.ThisAndForward);

        // Get participant information for user to assign-to
        AssociateCache  associateCache  =
AssociateCache.GetCurrent();
        AssociateRow    jimbo           =
associateCache.GetAssociate(associateCache.GetAssociateId("jimbo"));
        ParticipantInfo jimboParticipant= new
ParticipantInfo(jimbo.AssociateId, jimbo.PersonId, 2, 0, false);

        matrix.AssignTo( jimboParticipant );
        matrix.Save();
    }
```

```
    using SuperOffice.CRM.Entities;

    // Let the participant accept this one
    using (SoSession.Authenticate("tje3", "tje3"))
    {
        int assignedAppointmentId = 123;
        assignAccept = new AppointmentMatrix(assignedAppointmentId,
RecurrenceUpdateMode.ThisAndForward);
        RecurrenceDate firstDate =
assignAccept.InnerMatrix.GetRowKey(0);
        assignAccept.Accept();
        assignAccept.Save();
    }
```

See Also:

Appointment AppointmentMatrix AssociateCache
