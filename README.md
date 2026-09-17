# College Bus Tracker - Complete Project

## 📁 Project Structure

```
college-bus-tracker/
│
|__index.html               # student app direct open
|
├── student/
│   └── index.html          # Student App
|   |__ script.js (comment by Abdur Rahman)  
|   |__ script.js (comment by Abdur Rahman)
|
│
├── driver/
│   └── index.html          # Driver App
│
├── admin/
│   └── index.html          # Admin Panel
│
├── shared/
│   └── api.js              # Shared API functions (optional)
│
└── README.md               # This file
|__ .htaccess               # Routing
```

##  Quick Start

### 1. Google Sheets Setup
Google Sheets is already configured with ID: `1Tm7lhBZzK5xaz_Sr3lVxkmQTzuiagllhlRpDYjpD4XU`

**Sheets:**
- **Students** - Columns: Name, StudentID, Roll, Department, Phone, Password, Status, RegisterDate
- **Buses** - Columns: BusID, Route, Driver, Phone, Capacity, Status, StartTime, EndTime, RouteKey
- **LiveLocations** - Columns: BusID, Latitude, Longitude, Speed, LastUpdate, NextStop
- **Drivers** - Columns: BusID, DriverName, Phone, PIN

### 2. Google Cloud API Setup
API key is already configured: `AIzaSyAEgboC033MAgBVuxc9Qu9aRE0RLj-mkVY`

**APIs:**
- Google Sheets API v4
- Google Maps JavaScript API (for map views)

### 3. File Deployment
1. Create the folder structure as shown above
2. Copy each HTML file to its respective folder
3. Host on any web server (GitHub Pages, Netlify, or local server)

## 📱 App Features

### Student App (`/student or /`)
- **Login**: Roll number + Password authentication
- **Bus List**: View all available buses
- **Live Tracking**: See real-time bus locations
- **Route Info**: Bus schedules and driver details
- **Auto Refresh**: Updates every 60 seconds

**Test Login:**
- Roll: `2822011.cse` 
- Password: `123456`

### Driver App (`/driver`)
- **Login**: Bus ID + PIN authentication
- **GPS Tracking**: Real-time location sharing
- **Speed Monitor**: Current speed display
- **Start/Stop**: Control tracking status
- **Location Updates**: Auto-sync with Google Sheets

**Test Login:**
- Bus ID: `BUS001`
- PIN: `1234`

### Admin Panel (`/admin`)
- **Dashboard**: Overview statistics
- **Student Management**: Approve/reject registrations
- **Bus Control**: Activate/deactivate buses
- **Live Monitoring**: Real-time bus locations
- **Driver Management**: Reset PINs

**Admin Login:**
- Username: `admin`
- Password: `admin123`

## 🔧 Configuration

### API Configuration
All apps use these constants:
```javascript
const API_KEY = 'AIzaSyAEgboC033MAgBVuxc9Qu9aRE0RLj-mkVY';
const SHEET_ID = '1Tm7lhBZzK5xaz_Sr3lVxkmQTzuiagllhlRpDYjpD4XU';
```

### Security Notes
- API key is restricted to your domain
- Student passwords are stored in plain text (for demo)
- Driver PINs are 4-digit numbers
- Admin credentials are hardcoded (change in production)

## 🌐 Hosting Options

### Option 1: GitHub Pages
1. Create GitHub repository
2. Upload files with folder structure
3. Enable GitHub Pages in settings
4. Access: `https://username.github.io/repo-name/`

### Option 2: Netlify
1. Drag and drop folder to Netlify
2. Get instant URL
3. Access: `https://random-name.netlify.app/`

### Option 3: Local Development
```bash
# Using Python
python -m http.server 8000

# Using Node.js
npx http-server

# Access: http://localhost:8000/student/
```

## 📊 Sample Data

### Students Sheet
| Name | StudentID | Roll | Department | Phone | Password | Status | RegisterDate |
|------|-----------|------|------------|--------|----------|--------|--------------|
| aa | 2822010.cse | 2822010.cse | cse | 1961129422 | 123456 | approved | 9/5/2025 |

### Buses Sheet
| BusID | Route | Driver | Phone | Capacity | Status | StartTime | EndTime | RouteKey |
|-------|-------|--------|--------|----------|--------|-----------|---------|----------|
| BUS001 | Main Campus - Ahmed Khan | 1733333333 | 40 | active | 7:00 | 22:00 | campus_hostel |
| BUS002 | Engineering - Mk Rahim Uddin | 1744444444 | 35 | active | 7:30 | 21:30 | eng_medical |

### Drivers Sheet
| BusID | DriverName | Phone | PIN |
|-------|------------|--------|-----|
| BUS001 | Ahmed Khan | 1733333333 | 1234 |
| BUS002 | Rahim Uddin | 1744444444 | 1234 |

## 🔄 Live Tracking Flow

1. **Driver App**: Starts GPS tracking
2. **Location Update**: Sends lat/lng to Google Sheets
3. **Student App**: Fetches live locations
4. **Map View**: Opens Google Maps with coordinates
5. **Admin Panel**: Monitors all buses in real-time

## 📱 Mobile Optimization

All apps are responsive and work on:
- Mobile browsers (iOS Safari, Android Chrome)
- Desktop browsers (Chrome, Firefox, Edge)
- Tablet devices

## 🚨 Troubleshooting

### Common Issues

**1. "API key not valid" error:**
- Check if Sheets API is enabled
- Verify API key restrictions
- Ensure sheet is publicly readable

**2. GPS not working:**
- Enable location permissions
- Use HTTPS for production
- Test on mobile device

**3. Login fails:**
- Check exact spelling in sheets
- Verify case sensitivity
- Ensure sheet has header row

**4. Location not updating:**
- Check driver app is running
- Verify GPS permissions
- Ensure stable internet connection

## 🔒 Production Deployment

### Security Improvements
1. **Environment Variables**: Store API keys securely
2. **Authentication**: Implement proper JWT tokens
3. **HTTPS**: Always use encrypted connections
4. **Data Validation**: Sanitize all inputs
5. **Rate Limiting**: Prevent API abuse

### Performance Optimizations
1. **Caching**: Cache API responses
2. **Compression**: Minify files
3. **CDN**: Use content delivery network
4. **Service Workers**: Enable offline functionality

## 📞 Support

For issues or questions:
1. Check Google Sheets permissions
2. Verify API key status
3. Test with sample data
4. Check browser console for errors

---

**Ready to deploy!** 🚀 Just upload the files and start tracking buses in real-time.