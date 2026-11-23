# PE Class Assistant

A responsive, local-first class management app for physical education teachers. Built with React, TypeScript, Vite, Tailwind CSS, and Lucide icons. No account, server, or paid API required.

## Run locally

```bash
npm install
npm run dev
```

Open the local URL printed by Vite. Create a production build with `npm run build`, or preview it with `npm run preview`.

## Features

- Manage multiple class rosters, with unique student numbers per class; add, edit, deactivate through status, search, CSV import, and CSV export.
- Take attendance by date and class. Tap a number to cycle through present, absent, late, and excused; mark all present; reset with confirmation; attendance percentage updates immediately.
- Draw one or several eligible students. Fair rotation prioritizes lower participation counts; configure late eligibility and name reveal in Settings.
- Generate shuffled pairs with a trio, assistant, or observer option for odd numbers. Regenerate and swap pair members.
- Generate evenly distributed groups, move students manually between teams, and print.
- Browse and filter an activity library, choose a random activity, favorite activities, and add custom ones.
- Save/review lesson snapshots; export and restore a JSON backup; reset app data with confirmation.
- Changes are saved automatically in this browser's LocalStorage.

## Student CSV format

The first row is treated as a header. Columns are: `Student Number, Student Name, Class, Notes, Active`. Example:

```csv
Student Number,Student Name,Class,Notes,Active
1,Alex Morgan,Year 7,,Yes
2,Jamie Lee,Year 7,Left handed,Yes
```

Student numbers are unique within each class. Importing matching number/class entries updates those entries rather than duplicating them.

## Data and privacy

All roster, attendance, settings, and session data stays in browser LocalStorage on the device where it was entered. Clearing browser storage removes app data; use **Settings → Download JSON backup** to keep a copy. JSON restoration replaces the current data. CSV roster export contains student information, so handle the downloaded file appropriately.

## Notes

The initial roster is empty by design. Create a class roster and mark attendance before using participant selection or team tools. Attendance starts as absent for each date until changed. Session history records snapshots when **Save session** is selected.
