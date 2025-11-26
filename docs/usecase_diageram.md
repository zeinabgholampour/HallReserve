graph TD
    User -->|Login| System
    User -->|ViewRooms| System
    User -->|ReserveRoom| System
    User -->|CancelReservation| System
    Staff -->|ApproveReservation| System
    Staff -->|RejectReservation| System
    Admin -->|ViewReports| System