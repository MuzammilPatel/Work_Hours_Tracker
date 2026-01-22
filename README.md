# Work Hours Tracker

A standalone web application for tracking daily work hours, leave days, and managing weekly work-hour balances. Perfect for employees who need to track their time against a standard 38-hour work week with automatic calculations and carry-over balance management.

__NOTE: Code is developed by an AI agent__

## 📋 Overview

This application helps you:
- Log daily work hours with automatic lunch break deductions
- Track annual and personal leave days
- Monitor weekly progress toward your 38-hour target
- Manage carry-over hours (overtime or deficit) across weeks
- View historical data of completed weeks

## ✨ Key Features

### 🕐 Real-Time Clock & Date Display
- Live clock showing current time
- Current date with full weekday and date information
- Week number of the year (e.g., "Week 4")

### 📝 Work & Leave Entry Logging

#### Work Day Entry
- Log start and end times
- **Automatic deductions**:
  - 30 minutes lunch break (applied daily)
  - 1 hour on Fridays (for early finish)
- Calculates gross hours (total time) and net hours (after deductions)

#### Leave Entry (Annual & Personal)
- Track annual leave days
- Track personal leave days with custom hours
- Define exact hours used (e.g., 7.5 hours for full day, 3.75 for half day)
- No automatic deductions applied to leave hours

### 📊 Weekly Summary Dashboard

#### This Week (Actual)
- Shows total hours worked this week (work + leave combined)
- Updates in real-time as you add entries

#### Carry-Over Balance
- Displays accumulated overtime or deficit from previous weeks
- Green badge (+) for overtime hours
- Orange badge (-) for hours deficit
- Shows last update information

#### Hours Remaining
- Calculates how many hours you need to complete the week
- Adjusts based on your carry-over balance
- Green indicator when target is met (38 hours reached)
- Yellow indicator when hours remain

### 🔄 Automatic Week Rollover
- Detects when a new week starts automatically
- Calculates previous week's total hours
- Compares against 38-hour target
- Updates carry-over balance automatically
- Shows notification with rollover details
- No manual button clicking required!

### 📈 Week History Tracking
- View complete history of all completed weeks
- See hours worked, difference from target, and balance after each week
- Color-coded differences (green for overtime, orange for deficit)
- Sortable chronological display

### ✏️ Edit Entries
- Modify any logged entry (work or leave)
- Change date, times, or entry type
- Automatic recalculation of hours
- Updates weekly summary automatically

### 🔄 Balance Reset
- Manually reset carry-over balance to 0 if needed
- Confirmation prompt to prevent accidental resets
- Useful for starting fresh or correcting errors

### 💾 Persistent Data Storage
- All data saved automatically in browser's local storage
- Data persists across browser sessions
- No internet connection required after initial load
- Works completely offline

## 🚀 How to Use

### Installation

1. **Download the HTML file**
   - Save as `work-hours-tracker.html`

2. **Open the file**
   - Double-click to open in your default browser
   - Or right-click → "Open with" → Choose your browser

3. **Bookmark it** (Optional but recommended)
   - Press `Ctrl+D` (Windows/Linux) or `Cmd+D` (Mac)
   - For quick daily access

4. **Pin to taskbar/desktop** (Windows)
   - Right-click the file → "Create shortcut"
   - Drag shortcut to desktop or taskbar

### Daily Usage

#### Logging Work Hours

1. **Select Entry Type**: Choose "Work Day" (default)
2. **Pick Date**: Select the date you worked
3. **Enter Times**: Input start time and end time
4. **Add Entry**: Click "Add Entry" button

The app automatically:
- Deducts 30 minutes for lunch
- Deducts an additional 1 hour on Fridays
- Calculates net hours
- Updates weekly summary

#### Logging Leave

1. **Select Entry Type**: Choose "Annual Leave" or "Personal Leave"
2. **Pick Date**: Select the leave date
3. **Enter Hours**: Type the hours taken (e.g., 7.5 for full day)
4. **Add Entry**: Click "Add Entry" button

Leave hours count toward your weekly total without automatic deductions.

#### Editing an Entry

1. Click the **orange "Edit" button** next to any entry
2. Modify the date, times, or entry type as needed
3. Click **"Save Changes"** to update
4. Or click **"Cancel"** to close without saving

#### Viewing Week History

1. Click **"📊 View Week History"** button
2. Review past weeks' hours and balances
3. Click **"Close"** when done

#### Resetting Balance

1. Click **"🔄 Reset Balance"** button
2. Confirm the action in the popup
3. Carry-over balance returns to 0

## 📐 Calculation Logic

### Work Day Calculations

```
Gross Hours = End Time - Start Time
Net Hours = Gross Hours - 0.5 hours (lunch)

If Friday:
  Net Hours = Net Hours - 1 hour (early finish)
```

**Example (Monday)**:
- Start: 09:00, End: 17:30
- Gross: 8.5 hours
- Net: 8.5 - 0.5 = **8.0 hours**

**Example (Friday)**:
- Start: 09:00, End: 17:30
- Gross: 8.5 hours
- Net: 8.5 - 0.5 - 1.0 = **7.0 hours**

### Leave Day Calculations

```
Net Hours = Hours Entered (no deductions)
```

**Example**:
- Leave Type: Annual Leave
- Hours: 7.5
- Net: **7.5 hours**

### Weekly Balance

```
Target Hours = 38 hours per week
Carry-Over Balance = Previous balance + (Last week hours - 38)
Hours Remaining = 38 - (This week hours + Carry-over balance)
```

**Example Week 1**:
- Worked: 40 hours
- Difference: +2 hours
- New balance: **+2 hours**

**Example Week 2**:
- Current balance: +2 hours
- Worked so far: 30 hours
- Adjusted total: 30 + 2 = 32 hours
- Remaining: 38 - 32 = **6 hours**

## 🎨 Visual Guide

### Entry Types & Badges

| Entry Type | Badge Color | Indicator |
|------------|-------------|-----------|
| Work Day | Purple | -1h (Fridays only) |
| Annual Leave | Yellow | "Annual" |
| Personal Leave | Blue | "Personal" |

### Balance Indicators

| Status | Color | Meaning |
|--------|-------|---------|
| Positive Balance | Green | You have overtime hours |
| Negative Balance | Orange | You need to catch up |
| Target Met | Green | This week's 38 hours completed |
| Hours Remaining | Yellow | Still need to work more hours |

## 💡 Tips & Best Practices

1. **Log daily**: Enter your hours at the end of each day for accuracy
2. **Check weekly**: Monitor your progress throughout the week
3. **Review history**: Use week history to spot patterns
4. **Backup data**: Although data is saved locally, consider taking screenshots of important weeks
5. **Use same browser**: Your data is stored per-browser, so stick to one browser
6. **Don't clear cookies**: Clearing browser data will erase your logs

## ⚠️ Important Notes

### Data Storage

#### Where Your Data is Saved
Your work log is saved in your **browser's Local Storage**, which means:
- Stored on your computer in your browser's internal database
- **NOT** saved in the HTML file itself
- **NOT** stored on any cloud or server
- **NOT** synced between devices or browsers

#### Storage Locations by Browser

**Windows:**
- **Chrome/Edge**: `C:\Users\[YourName]\AppData\Local\Google\Chrome\User Data\Default\Local Storage`
- **Firefox**: `C:\Users\[YourName]\AppData\Roaming\Mozilla\Firefox\Profiles\[profile]\storage\default`

**Mac:**
- **Chrome**: `~/Library/Application Support/Google/Chrome/Default/Local Storage`
- **Safari**: `~/Library/Safari/LocalStorage`

**Linux:**
- **Chrome**: `~/.config/google-chrome/Default/Local Storage`
- **Firefox**: `~/.mozilla/firefox/[profile]/storage/default`

#### What Gets Stored
The app saves these items in localStorage:
- `workEntries` - All your work and leave entries
- `carryOver` - Your carry-over balance
- `weekHistory` - History of completed weeks
- `lastProcessedWeek` - Last week that was processed

#### Key Storage Facts
- ✅ Data persists between browser sessions (survives closing browser)
- ✅ Each browser has separate storage (Chrome data ≠ Firefox data)
- ❌ Clearing browser data/cookies will delete your entries permanently
- ❌ Incognito/Private mode does NOT save data
- ❌ No cloud sync or automatic backup
- ❌ Data cannot be transferred between browsers automatically

#### How to Protect Your Data
1. **Use the same browser consistently** - Pick Chrome, Firefox, or Edge and stick with it
2. **Don't clear browser data** - Be careful when clearing cookies/cache
3. **Take regular screenshots** - Backup important weeks manually
4. **Avoid incognito mode** - Data won't be saved in private browsing
5. **Export data regularly** - Use browser developer tools to backup localStorage if needed

### Browser Compatibility
- Works in all modern browsers:
  - ✅ Chrome/Edge (recommended)
  - ✅ Firefox
  - ✅ Safari
  - ✅ Opera

### Privacy & Security
- ✅ All data stays on your computer
- ✅ No internet connection required (offline-capable)
- ✅ No data sent to any server
- ✅ No tracking or analytics
- ✅ Completely private

## 🔧 Troubleshooting

### Problem: My data disappeared
**Solution**: Check if you:
- Switched browsers
- Cleared browser data/cookies
- Used incognito/private mode (data doesn't persist)

### Problem: Buttons not working
**Solution**: 
- Refresh the page (F5)
- Ensure JavaScript is enabled in your browser
- Try opening in a different browser

### Problem: Wrong calculations
**Solution**:
- Verify start/end times are correct
- Check if Friday deduction applied correctly
- Use Edit feature to correct entries

### Problem: Week didn't rollover
**Solution**:
- Make sure you open the app in the new week
- Rollover happens automatically when app detects new week
- Refresh the page if needed

## 📊 Example Workflow

### Monday
- Log: 09:00 - 17:30 (8.0h net)
- Weekly total: 8.0h
- Remaining: 30.0h

### Tuesday
- Log: 09:00 - 17:30 (8.0h net)
- Weekly total: 16.0h
- Remaining: 22.0h

### Wednesday
- Log: 09:00 - 17:30 (8.0h net)
- Weekly total: 24.0h
- Remaining: 14.0h

### Thursday
- Log: 09:00 - 17:30 (8.0h net)
- Weekly total: 32.0h
- Remaining: 6.0h

### Friday
- Log: 09:00 - 17:00 (7.0h net with auto deductions)
- Weekly total: 39.0h
- Status: Target met! 🎉
- Carry-over: +1.0h for next week

## 🆘 Support

Since this is a standalone HTML file with no server backend:
- No email or phone support available
- Refer to this README for guidance
- Check browser console for error messages (F12)

## 📄 License

This is a free, open-source tool. Feel free to modify and share!

## 🎯 Version

**Current Version**: 1.0
**Last Updated**: January 2026

---

**Happy Time Tracking! 🚀**# Work_Hours_Tracker
A standalone web application for tracking daily work hours, leave days, and managing weekly work-hour balances. Perfect for employees who need to track their time against a standard 38-hour work week with automatic calculations and carry-over balance management.
