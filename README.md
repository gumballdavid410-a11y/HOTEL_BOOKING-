[README (1).md](https://github.com/user-attachments/files/34261743/README.1.md)
# Assignment 8 – My Hotel Booking Chatbot Intent Dataset

**Student:** Rangira Rurangwa David  
**Course:** Chatbots Development (AITCD001), Week 8  
**Project:** Provisional Hotel Booking Chatbot  
**Dataset status:** Synthetic prototype; original Portfolio Project 1 rules not verified.

> **Academic-integrity disclosure:** All 180 messages in `intents.csv` are synthetic examples created for this prototype. None were collected from real people. No UNMATCHED log or Step 10 local-phrasing records were supplied. The original Portfolio Project 1 Hotel Booking Chatbot source code was not available for verification. Therefore, the intents and baseline rules are provisional and must not be described as the original chatbot's verified functionality.

## 1. Intent dataset title

**Hotel Booking Chatbot – Provisional Intent Dataset (Synthetic)**

I prepared 180 unique text messages across six labels, with 30 messages per label.

## 2. Labels, meanings and message counts

| Label | Meaning | Messages |
|---|---|---:|
| `room_availability` | Asks whether a room is free or available | 30 |
| `room_booking` | Requests a new hotel room reservation | 30 |
| `booking_modification` | Changes or updates an existing reservation | 30 |
| `booking_cancellation` | Cancels an existing reservation | 30 |
| `hotel_amenities` | Asks about hotel facilities or services | 30 |
| `out_of_scope` | Request outside the five supported hotel topics | 30 |
| **Total** | **6 labels** | **180** |

Largest/smallest label ratio: **1.00** (maximum permitted: 1.50).

## 3. Labelling guideline

1. Use `booking_cancellation` when the main request is to cancel, remove, withdraw or stop an existing reservation.
2. Use `booking_modification` when the user wants to change, update, extend, move or amend an existing booking without cancelling it.
3. Use `room_availability` when the user asks whether a room is vacant, free, open or available; an availability question is not itself a booking.
4. Use `hotel_amenities` for questions about facilities or services such as Wi-Fi, breakfast, parking, pool, gym or laundry.
5. Use `room_booking` when the user wants to create, reserve or make a new room reservation.
6. Use `out_of_scope` when the main request is unrelated to the five supported hotel topics.
7. If more than one topic appears, label the main requested action; cancellation takes priority over modification, and an availability question alone is not a booking.
8. Preserve the exact message text, spelling, abbreviations, Kinyarwanda, mixed language and SMS style. Do not translate or silently correct messages.

## 4. Message sources and counts

| Source | Count | Notes |
|---|---:|---|
| Synthetic examples | 180 | All rows in the CSV are explicitly marked `synthetic` |
| Real people | 0 | Not collected or claimed |
| UNMATCHED log | 0 | Not provided |
| Step 10 local phrasing | 0 | Not provided |
| **Total** | **180** | |

Each intent has 6 Kinyarwanda, 6 mixed-language and 6 SMS-style coverage-tagged examples, alongside English examples. `language_style` is an editorial coverage tag, not evidence of real-world collection.

## 5. Quality check

The quality checks in my notebook report:

- PASS — At least 30 messages per label: 30 each.
- PASS — Largest/smallest label ratio <= 1.5: 1.00.
- PASS — No duplicate messages: 0.
- PASS — Only approved labels: six approved labels, no extras.
- PASS — Every label includes Kinyarwanda, mixed and SMS-style coverage.
- PASS — All rows transparently marked synthetic.

**Last six lines of the quality report:**
```text
Unique messages: 180
Unknown labels: []
Label balance ratio: 1.00
Genuine people messages: 0
Synthetic messages: 180
Language-style coverage by label: English, Kinyarwanda, mixed, SMS-style
```

## 6. Training and test split

I created a stratified 80/20 split with `random_state=42`.

- Training set: **144 messages** (80%)
- Test set: **36 messages** (20%)

## 7. Original rules baseline and incorrect predictions

**This is not the original Portfolio Project 1 baseline.** It evaluates only the provisional keyword rules in the notebook because the original Hotel Booking Chatbot code was not verified.

- Correct test predictions: **32 / 36**
- Provisional rule accuracy: **88.9%**
- Incorrect predictions: **4**

Examples of incorrect predictions:

- Message: `Is there free parking for guests?` — actual: `hotel_amenities`, predicted: `room_availability`.
- Message: `Ese mufite chambre iboneka ku Tuesday?` — actual: `room_availability`, predicted: `out_of_scope`.
- Message: `Can u delete my hotel reservation?` — actual: `booking_cancellation`, predicted: `room_booking`.
- Message: `Please remove my booking from the system.` — actual: `booking_cancellation`, predicted: `booking_modification`.

## 8. Entities and their counts

I used a simple regular-expression entity ruler. Counts are mention counts over all 180 messages, not unique-message counts.

| Entity | Meaning | Mentions |
|---|---|---:|
| `LOCATION` | Hotel location/place name | 2 |
| `ROOM_TYPE` | Room category | 21 |
| `DATE` | Date or date phrase | 44 |
| `GUEST_COUNT` | Number of guests | 10 |

This is a lightweight demonstration, not a trained entity-recognition model.

## 9. What is still weak in the dataset

1. **No genuine user data:** the requirement for at least 20 real-person messages is not met.
2. **No project logs:** UNMATCHED and Step 10 messages were not provided.
3. **Unverified intent inventory:** the original Portfolio Project 1 code was not available, so these six labels are provisional.
4. **Unverified original baseline:** 88.9% is the accuracy of this notebook's provisional keyword rules only.
5. **Synthetic language coverage:** Kinyarwanda and mixed-language examples need review by fluent speakers.
6. **Simple entity ruler:** regular expressions can miss unseen spellings, locations, room types and date formats.
7. **Limited diversity:** 30 examples per label is a minimum-sized prototype and may not represent real guest requests.

## 10. Remaining limitations and next work

- The dataset still needs at least 20 genuine, anonymised messages collected with consent. Their exact wording and source must be preserved accurately.
- Actual UNMATCHED and Step 10 examples from Portfolio Project 1 have not yet been added.
- The original Hotel Booking Chatbot code still needs to be checked so provisional intents and rules can be replaced with verified ones.
- The notebook has been run from beginning to end for this synthetic prototype. It must be run again if the dataset or rules change.
- The final files can be submitted through Google Classroom after the missing project evidence and genuine messages are added.

**Do not present this synthetic prototype as satisfying the genuine-message requirement or as a verified reproduction of Portfolio Project 1.**
