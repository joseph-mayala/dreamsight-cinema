# DreamSight Cinema

A console-based cinema booking and management system written in Python. One program serves four roles
(customer, ticketing clerk, cinema manager and technician), each with its own login and menu.

Built as a university coursework project at Asia Pacific University (APU). It uses only the Python standard
language features: no external libraries, and all data is stored in plain text files.

## What each role can do

| Role | Features |
|---|---|
| **Customer** | Register with input validation and a unique-email check, log in, browse movies, book seats, pay, view booking history, update profile |
| **Ticketing clerk** | Book tickets for walk-in customers, cancel or modify a booking, view seats and showtimes, take payment (cash, debit card, credit card, e-wallet), generate a receipt |
| **Cinema manager** | Add, update, remove and view movies and showtimes, set ticket prices and discount policy, view a summary |
| **Technician** | View upcoming screenings and equipment status, report and update issues (projector, sound, AC), view the issue log |

## How it works

- **Seat map.** Each auditorium's layout is read from `Auditoriums.txt` and drawn in the terminal. Seats show as
  `[ ]` available, `[O]` selected or `[X]` reserved. Reserved seats are tracked per showtime in
  `Reserved_seats.txt`, so the same seat cannot be booked twice for one show.
- **Bookings and payments.** Booking and payment IDs are generated from the last ID on file. Each payment is
  recorded with its method and date, and a receipt can be printed for any booking.
- **Equipment and readiness.** An auditorium is marked `Ready` or `Not Ready` from the state of its projector,
  sound and AC. When a technician resolves an issue, the auditorium's status is updated.
- **Storage.** Every record lives in a comma-separated text file that is read and rewritten by the program.

## Run it

You need Python 3 (tested on 3.13). The program reads its data files by relative path, so run it from inside the
`CINEMAPYP` folder:

```
cd CINEMAPYP
python Cinema_System.py
```

Pick a role from the main menu. Staff logins are in the matching `*_auth.txt` file; customers can register a
new account from the customer menu.

## Files

| File | Purpose |
|---|---|
| `Cinema_System.py` | The full program: all four roles and the main menu |
| `Customer_System.py`, `Ticketing_Clerk_System.py`, `Technician_System.py` | Earlier stand-alone versions of single modules, kept for reference |
| `Movies.txt`, `Showtimes.txt`, `Auditoriums.txt` | Movies, the weekly schedule and auditorium layouts |
| `Bookings.txt`, `Payments.txt`, `Reserved_seats.txt` | Bookings, payments and the seats taken for each show |
| `Discount.txt`, `Issue_report.txt` | Discount rates and the technician's issue log |
| `*_auth.txt` | Sample login data for each role |

## Limitations

- Passwords are stored in plain text. This is a coursework exercise in file handling, not a secure system.
- Movie titles and dates must be typed exactly as shown.
- All data is sample data.
