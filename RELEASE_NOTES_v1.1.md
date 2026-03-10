# PRVS Dashboard v1.1 Release Notes
**Released:** March 10, 2026

## 🎉 Major Features

### Tech Check-In Button
- **Direct access**: Neon green "Tech Check In" button on every RO tile
- **No QR needed**: Click to open check-in page with RO pre-filled
- **Two paths**: Use QR code OR button for maximum flexibility

### Admin-Only Expanded View
- **Restricted access**: Expanded view now admin-only
- **Financial visibility**: Total Value and Filtered Value stats appear only in Expanded view
- **Permission control**: Non-admin users see Condensed and Regular views only

### Dynamic Stats Bar
- **Smart filtering**: Stats adapt to active filters
- **Condensed/Regular**: Shows Total RVs + selected status counts + Avg Days
- **Space efficient**: Multiple status filters combined in single card
- **Expanded (Admin)**: Full stats including In Progress, Awaiting Parts

### Heat Map Color Coding
- **Visual urgency**: Days on lot display with gradient heat colors
- **0-30 days**: Default color
- **31-40 days**: 🟠 Orange
- **41-50 days**: 🔴 Orange-red  
- **51-60 days**: 💗 Red-pink
- **61+ days**: 💖 Neon pink (hottest)
- **Applied to**: RO tile badges AND "Longest Wait" stat card

### Longest Wait Stat
- **New metric**: Shows maximum days on lot across all RVs
- **Heat colored**: Automatically applies gradient based on age
- **Quick visibility**: Spot the oldest RV at a glance

## 📊 Updates & Improvements

### Status System Overhaul
- **Renamed statuses**:
  - "Completed" → "Repairs Completed"
  - "Quality Check" → "Waiting for QA/QC" (neon pink)
- **Updated progress mapping**:
  - Not On Lot: 0%
  - On Lot: 10%
  - Awaiting Approval: 20%
  - Awaiting Parts: 30%
  - In Progress: 60%
  - Repairs Completed: 80%
  - Waiting for QA/QC: 85%
  - Ready for Pickup: 95%
  - Delivered/Cashed Out: 100%

### Mobile Experience
- **Fixed layout**: Filter sections stack properly on mobile
- **Touch friendly**: All buttons sized for mobile interaction
- **RV photos**: Fixed loading in Condensed view on all devices

### Preset Updates
- **Condensed default**: New users start in Condensed view
- **Updated config**:
  - Condensed: RV Photo ON, Dollar Value OFF
  - Regular: All features except time logs
  - Expanded: Everything (admin only)

### Data & Performance
- **Total RVs**: Now shows filtered count (adapts to active filters)
- **Time logs fix**: Properly loads with persistent login
- **Removed repair type**: "Multi" removed from system

## 🐛 Bug Fixes
- Fixed time logs not loading on saved token authentication
- Fixed RV photos not appearing in Condensed view (Safari desktop)
- Fixed async/await issues in token loading
- Fixed mobile filter layout breaking on small screens

## 📝 Documentation
- All files versioned to v1.1
- Console logging updated
- Footer version display updated

## 🚀 Deployment Notes
1. Download `index-updated.html` and `checkin.html`
2. Rename `index-updated.html` → `index.html`
3. Upload both to GitHub repo
4. Wait 2 minutes for GitHub Pages deployment
5. Hard refresh: Command+Shift+R (Mac) or Ctrl+Shift+F5 (Windows)
6. Clear cache if needed:
   ```javascript
   localStorage.clear();
   sessionStorage.clear();
   location.reload();
   ```

---

**Previous version:** v1.0 (March 9, 2026)
**Next planned:** v1.2 - Photo repository system
