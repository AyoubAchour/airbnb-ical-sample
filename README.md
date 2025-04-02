# Airbnb iCal Sample Calendar

This repository contains a sample Airbnb iCal calendar file that accurately represents the current format used by Airbnb's calendar export functionality. This sample is perfect for testing calendar synchronization features in your applications.

## Sample Calendar Files

### Villa Hammamet Calendar
- **Filename:** `villa_hammamet.ics`
- **Direct URL for testing:** [https://raw.githubusercontent.com/AyoubAchour/airbnb-ical-sample/main/villa_hammamet.ics](https://raw.githubusercontent.com/AyoubAchour/airbnb-ical-sample/main/villa_hammamet.ics)

## Usage in Your Application

You can use this sample iCal URL for testing your calendar synchronization implementation:

```javascript
// Example using node-ical in Next.js
import ical from 'node-ical';

async function fetchCalendar() {
  const url = 'https://raw.githubusercontent.com/AyoubAchour/airbnb-ical-sample/main/villa_hammamet.ics';
  const events = await ical.fromURL(url);
  
  // Process the events
  for (const key in events) {
    const event = events[key];
    if (event.type === 'VEVENT') {
      console.log('Reservation:', {
        start: event.start,
        end: event.end,
        summary: event.summary,
        description: event.description
      });
    }
  }
}
```

## Sample Calendar Details

The calendar sample includes:

- Properly formatted Airbnb iCal headers
- Multiple bookings across different months of 2025-2026
- All standard Airbnb data fields:
  - Check-in and check-out dates
  - Number of nights
  - Guest phone numbers (fictional)
  - Guest email addresses (fictional)
  - Property name
  - Number of guests
- Proper UID format with @airbnb.com suffix
- Summary format matching Airbnb's standard format

## Testing Tools

You can validate and view this iCal feed using:

1. **iCalendar.org Validator**: [https://icalendar.org/validator.html](https://icalendar.org/validator.html)
2. **Google Calendar**: Import the URL into Google Calendar
3. **iCal Link Viewer**: [https://calendargeek.com/](https://calendargeek.com/)

## License

This sample is provided under the MIT License for testing purposes.

## Disclaimer

This is a sample file for testing purposes only. All guest data is fictional. The format accurately matches Airbnb's iCal export format but is not affiliated with or endorsed by Airbnb.
