**Before you start.** Installing this addon does not assign users to the **Calendar Export Ics** access group, so **Export to Ics File** is hidden by default. In developer mode, an administrator can open **Settings → Users & Companies → Groups**, find that group, and add your user. You also need access to Calendar Configuration.

To check the export with events whose details you know:

1. In **Calendar**, create two future timed events and one future all-day event. Give each a distinct title, include yourself as an attendee, and note their start and end dates and times.
2. Open **Calendar → Configuration → Export to Ics File**.
3. Set **End Export Date** to the date of the last test event or later. Leave it empty to include all future events from your calendar.
4. Select **Generate ICS File** and download the resulting `.ics` file.
5. Open the file in a text editor. It should contain one `VCALENDAR` with a `VEVENT` for each included event. Check each `SUMMARY` against its title and each `DTSTART` and `DTEND` against its dates and times. Timed values can be written in UTC rather than your displayed time zone; an all-day event uses dates, and its ICS end date is the day after the final day shown in Odoo.

The export includes other future events for which you are an attendee, so the file can contain more events than the three test events. Events without your attendee record are not included.
