# Calorietracker Changelog

---

## [Unreleased]
- bodyfat % calculator and body measurement tracking
- share analytics directly to social media (fb/twitter/ig)
- exercise tracking with fitness progression analytics
- food diary with nutrition tracking using OpenFoodFacts

## 2020-12-21
### Added
- Roles: coaches and clients! 
- Users can now assign friends to the "Coach" role from the friends tab
- Coaches are able to view all of their clients analytics data from the clients tab
- Friend list badges to display role
- Log and add another log button

### Changed
- Pending friend requests can be canceled

### Fixed
- Percent to goal on analytics page
- friend request already exists handling

## 2020-12-07
### Added
- Announcement system - users can recieve dismissable announcements
- Messaging system - users can send and recieve messages to their friends
- Notification system - users can recieve notifications

### Changed
- Analytics weekly summary now shows median instead of average weekly weight
- Analytics TDEE calculation should be more dynamic and robust

### Fixed
- CSV import now handles decimals for calories in
- Topbar responsiveness on mobile

## 2020-11-12
### Added
- 2 Factor Authentication support!
- Favicon.ico and apple-touch-icon.png url routing
- Custom 404 and 500 Error Pages
- Input streak flame and gold coin to topbar

### Changed
- Login buttons now comply with Google Oauth branding guidelines for sign in with Google

### Fixed
- Creating a new log will default unit selection based on user's unit preferences and date to today's date

## 2020-11-09
### Added

- Friends page - add friends & view each other's profiles!
- Profile page - check out your own profile
- Share your analytics to social media using share button
- MyFitnessPal autosync - MFP logs can be automatically imported

### Changed

- Cleaned up UI - Log buttons, font-weight and colors
- Redirect to analytics over landing page when user is logged in
- CSV upload errors will now display to users without 500-ing

### Fixed

- Numerous MFP import bugs relating to unhandeled measurement types
- Default goal weight, dates should be dynamic based a user's join date

## 2020-10-29

### Added

- landing page!
- sign in with google
- download jpgs of analytics graphs buttons
- referral program
- hover effect on profile name topbar
- up to 3 progress pics per log entry

### Changed

- migrated feedback, logout buttons from sidebar to topbar profile dropdown
- updated footer
- standardized card use for forms etc.

## 2020-10-22

### Added

- progress pics storage in logs using cloudinary
- oauth2 logins via facebook, discord
- deletion of logs
- import logs via csv
- favicon
- implemented a privacy policy
- this changelog!
- username dropdown menu in topbar

### Changed

- feedback form description
- level of email error logging
- weekly summaries flexwidth on analytivs dashboard
- registered copyright in footer

---

### [Style Guide](https://keepachangelog.com/en/1.0.0/)

**Added** for new features.

**Changed** for changes in existing functionality.

**Deprecated** for soon-to-be removed features.

**Removed** for now removed features.

**Fixed** for any bug fixes.

**Security** in case of vulnerabilities.
