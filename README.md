# RecycloScan - Smart Recycling Management App

## 📱 App Description

RecycloScan is an innovative iOS application designed to revolutionize household recycling management. The app combines AI-powered waste classification with intelligent bin collection scheduling, gamification, and smart notifications to help users maintain an effective recycling routine while earning points for their environmental efforts.

**Target Audience:** Households and individuals looking to improve their recycling habits and never miss a bin collection day.

**Platform:** iOS 16.0+

**Language:** Swift 5.0+ with SwiftUI

---

## ✨ Features and Functionalities

### 1. **AI-Powered Waste Scanner** 🤖
- **Real-time Camera Classification**: Uses CoreML and Vision frameworks to identify recyclable items
- **Supported Categories**:
  - Plastic containers and bottles
  - Paper products and cardboard
  - Metal cans and containers
  - Glass bottles and jars
  - Organic/compostable waste
  - E-waste (electronics)
  - General waste
- **Instant Feedback**: Provides immediate classification results with confidence scores
- **Item Tracking**: Automatically adds scanned items to your pending collection list

### 2. **Smart Bin Collection Scheduler** 📅
- **Multi-Bin Management**: Supports 4 color-coded bin types:
  - 🔴 **Red Bin**: General waste
  - 🟡 **Yellow Bin**: Mixed container recycling
  - 🔵 **Blue Bin**: Paper & cardboard
  - 🟢 **Green Bin**: Garden & vegetation waste
- **Customizable Schedules**: Set pickup days for each bin type (any day of the week)
- **Next Pickup Display**: Always know which bin goes out next and when
- **Weekly Calendar View**: See all upcoming collections at a glance
- **Toggle Enable/Disable**: Quickly enable or disable specific bin schedules

### 3. **Intelligent Notification System** 🔔
- **Timely Reminders**: Customizable notification timing (1-24 hours before collection)
- **Interactive Push Notifications**: 
  - **Yes/No Action Buttons**: Confirm bin placement directly from notifications
  - **Press-and-Hold**: Reveal action buttons on lock screen
  - **Foreground Alerts**: Receive notifications even when app is active
- **Bin-Specific Categories**: Different notification types for each bin color
- **Weekly Recycling Tips**: Educational notifications with helpful recycling advice
- **Test Notification Feature**: Unique testing tool to verify notification setup (15-second delivery)

### 4. **Comprehensive Statistics & Gamification** 🎮
#### Per-Bin Statistics:
- **Total Points Earned**: Track points accumulated for each bin type
- **Current Streak**: Count consecutive successful pickups
- **Best Streak**: Personal record for longest streak
- **Completed Pickups**: Total successful collections
- **Missed Pickups**: Track missed collection days
- **Success Rate**: Percentage-based performance metric
- **Last Pickup Date**: When the bin was last collected

#### Overall Statistics:
- **Total Recycling Points**: Cumulative score across all activities
- **Items Recycled**: Total count of scanned recyclable items
- **Pickup History**: Detailed log of all collections with dates and points
- **Category Breakdown**: See which materials you recycle most
- **Environmental Impact**: Visualize your recycling contribution

### 5. **Pending Collection Management** 📦
- **Item Queue**: View all scanned items awaiting pickup
- **Potential Points Display**: See how many points you'll earn
- **Category Breakdown**: Items sorted by recyclable type
- **Remove Items**: Swipe to remove items from pending list
- **Visual Cards**: Color-coded cards for each item with icons

### 6. **Notification Center** 📬
- **Three Filter Tabs**:
  - **Active**: Current pending notifications
  - **Completed**: Successfully acted upon notifications
  - **Missed**: Overdue or declined notifications
- **Interactive Cards**: 
  - Tap-and-hold for quick Yes/No responses
  - Visual animations and haptic feedback
  - Color-coded status badges
- **Completion Statistics**: Track your notification response rate
- **Empty State Messages**: Encouraging feedback when lists are empty

### 7. **Modern UI/UX Design** 🎨
- **Color Theme System**:
  - Forest Green primary color
  - Bin-specific accent colors (Red, Yellow, Blue, Green)
  - Warm Orange for highlights
  - Beige backgrounds for comfort
  - White surfaces for content cards
- **Typography System**: Custom text styles for consistency
- **Smooth Animations**: Spring animations, fade transitions, scale effects
- **Shadow Effects**: Subtle shadows for depth and hierarchy
- **Haptic Feedback**: Touch response for interactive elements
- **Dark Mode Compatible**: Adapts to system appearance settings

---

## 👥 User Instructions

### Getting Started

#### 1. **First Launch Setup**
```
1. Open RecycloScan
2. Grant Camera Permission (required for scanning)
3. Grant Notification Permission (recommended)
4. Set up your bin collection schedule
```

#### 2. **Scanning Items**
```
1. Tap the "Scan" tab or camera icon
2. Point camera at recyclable item
3. Wait for automatic detection (1-2 seconds)
4. Review classification result
5. Item automatically added to pending collection
```

#### 3. **Setting Up Bin Schedules**
```
1. Navigate to "Pickup Appointment" tab
2. Tap on any bin card (Red, Yellow, Blue, or Green)
3. View your statistics for that bin
4. Select pickup days by tapping days of the week
5. Adjust notification reminder time (1-24 hours before)
6. Optional: Tap "Send Test Notification" to verify setup
7. Tap "Save" to confirm changes
```

#### 4. **Managing Notifications**
```
1. Go to "Notifications" tab
2. View active, completed, or missed notifications
3. For active notifications:
   - Tap "Yes" if you put the bin out
   - Tap "No" if you missed it
   - Or press-and-hold for quick actions
4. Track your completion rate in the stats card
```

#### 5. **Scheduling a Pickup**
```
1. Scan items throughout the week
2. View pending items in "Pending Collection" tab
3. See potential points you'll earn
4. When collection day arrives:
   - Respond to notification
   - Confirm bins were put out
   - Points are automatically awarded
```

#### 6. **Tracking Your Progress**
```
1. Open "Your Points" tab
2. View total points at the top
3. Scroll to see:
   - Quick stats grid (items recycled, pickups, etc.)
   - Category breakdown by material type
   - Recent pickup history
4. Set personal goals based on statistics
```

### Pro Tips 💡

**Maximize Your Points:**
- Scan items regularly, even small ones
- Never miss a bin collection day
- Build long streaks for each bin type
- Learn from weekly recycling tips

**Notification Best Practices:**
- Set reminder time based on your routine
- Test notifications after setup
- Always respond to notifications (yes or no)
- Enable press-and-hold for faster responses

**Efficient Scanning:**
- Ensure good lighting
- Hold camera steady for 1-2 seconds
- Scan items individually for accuracy
- Clean items before scanning for better recognition

---

## 🔧 Technical Details

### Architecture

#### Design Pattern: MVVM (Model-View-ViewModel)
```
┌─────────────────────────────────────────┐
│              Views (SwiftUI)            │
│  - ContentView                          │
│  - WasteScannerView                     │
│  - PickupAppointmentView                │
│  - NotificationCenterView               │
│  - PendingCollectionView                │
│  - PointsStatsView                      │
└─────────────┬───────────────────────────┘
              │
              ↓
┌─────────────────────────────────────────┐
│          ViewModels (Logic)             │
│  - CameraManager                        │
│  - ScannerClassifierViewModel           │
│  - PickupSchedulerVM                    │
│  - NotificationManagerVM                │
│  - RecyclingManager                     │
└─────────────┬───────────────────────────┘
              │
              ↓
┌─────────────────────────────────────────┐
│          Models (Data)                  │
│  - BinType                              │
│  - RecyclableItem                       │
│  - NotificationItem                     │
│  - PickupEvent                          │
│  - PickupSchedule                       │
└─────────────────────────────────────────┘
```

### Core Technologies

#### 1. **Machine Learning**
- **Framework**: CoreML
- **Model**: WasteClassifierOneMLModel.mlmodel
- **Vision Framework**: For image preprocessing
- **Real-time Processing**: AVFoundation camera integration
- **Classification**: 7 waste categories with confidence scores

#### 2. **Notifications**
- **Framework**: UserNotifications (UNUserNotificationCenter)
- **Features**:
  - Interactive notifications with custom actions
  - Notification categories (BIN_REMINDER, WEEKLY_TIP, TEST_NOTIFICATION)
  - Delegate pattern for response handling
  - Calendar-based triggers
  - Time interval triggers for testing
  - Badge management

#### 3. **Data Persistence**
- **UserDefaults**: For lightweight data storage
  - Pickup schedules
  - Notification history
  - Statistics and streaks
  - Pending items
  - User preferences
- **Codable Protocol**: For encoding/decoding complex types
- **JSON Serialization**: For structured data storage

#### 4. **Camera & Vision**
- **AVFoundation**: Camera capture and preview
- **AVCaptureSession**: Video input management
- **Vision Framework**: Image analysis and ML integration
- **Real-time Processing**: Continuous frame analysis
- **Error Handling**: Camera permission and availability checks

### Key Classes & Their Responsibilities

#### ViewModels

**1. PickupSchedulerVM**
```swift
Responsibilities:
- Manage bin collection schedules
- Track statistics per bin type (streaks, completions, misses)
- Calculate next pickup dates
- Schedule notifications via NotificationManagerVM
- Persist schedule data to UserDefaults
- Calculate overall completion rates

Key Properties:
- pickupSchedule: PickupSchedule
- binCompletionStats: [BinType: BinStats]
- recyclingManager: RecyclingManager?
- notificationManager: NotificationManagerVM?
```

**2. NotificationManagerVM (NSObject, ObservableObject)**
```swift
Responsibilities:
- Request and manage notification permissions
- Setup interactive notification categories
- Schedule bin reminder notifications
- Schedule weekly tip notifications
- Handle notification responses via delegate
- Track notification completion rates
- Award points for confirmed pickups

Conforms to: UNUserNotificationCenterDelegate

Key Properties:
- notifications: [NotificationItem]
- notificationPermissionGranted: Bool
- pickupScheduler: PickupSchedulerVM?
- recyclingManager: RecyclingManager?
```

**3. RecyclingManager**
```swift
Responsibilities:
- Track scanned items in pending collection
- Manage pickup history
- Calculate and award points
- Maintain total points counter
- Record bin completion events
- Generate statistics by waste type

Key Properties:
- totalPoints: Int
- pendingItems: [RecyclableItem]
- pickupHistory: [PickupEvent]
```

**4. ScannerClassifierViewModel**
```swift
Responsibilities:
- Interface with CoreML model
- Process camera frames
- Classify waste items
- Provide confidence scores
- Handle classification errors
```

**5. CameraManager**
```swift
Responsibilities:
- Manage AVCaptureSession
- Handle camera permissions
- Provide video preview layer
- Capture and process frames
- Handle camera lifecycle
```

#### Models

**1. BinType (Enum)**
```swift
Cases: red, yellow, blue, green
Properties:
- displayName: String
- wasteType: String
- color: Color
- icon: String
- description: String
```

**2. BinStats (Struct)**
```swift
Properties:
- completedPickups: Int
- missedPickups: Int
- currentStreak: Int
- bestStreak: Int
- totalPointsEarned: Int
- lastPickupDate: Date?

Computed:
- completionRate: Double
```

**3. NotificationItem (Struct)**
```swift
Properties:
- id: UUID
- type: NotificationType
- title: String
- message: String
- scheduledDate: Date
- response: NotificationResponse
- respondedDate: Date?
- binType: BinType?
- tipCategory: String?

Methods:
- markAsCompleted()
- markAsMissed()
- isOverdue: Bool
- isActive: Bool
```

**4. PickupSchedule (Struct)**
```swift
Properties:
- binSchedules: [BinSchedule]
- notificationsEnabled: Bool
- reminderTimeBeforePickup: TimeInterval
- lastUpdated: Date

Methods:
- schedule(for:) -> BinSchedule?
- nextPickup() -> (BinType, Date)?
- upcomingPickups(days:) -> [(BinType, Date)]
- hasPickupToday() -> Bool
- todayPickups() -> [BinType]
```

### Data Flow

#### 1. Scanning Flow
```
User taps camera
    ↓
CameraManager initializes AVCaptureSession
    ↓
Camera frames sent to ScannerClassifierViewModel
    ↓
CoreML model classifies waste type
    ↓
Classification result returned to WasteScannerView
    ↓
RecyclingManager.addScannedItem() called
    ↓
Item added to pendingItems array
    ↓
Data persisted to UserDefaults
```

#### 2. Notification Flow
```
User sets bin schedule
    ↓
PickupSchedulerVM.updatePickupDays() called
    ↓
Schedule saved to UserDefaults
    ↓
PickupSchedulerVM triggers scheduleNotifications()
    ↓
NotificationManagerVM.scheduleAllBinReminders() called
    ↓
For each upcoming pickup (next 14 days):
    - Calculate notification date (pickup date - reminder hours)
    - Create UNMutableNotificationContent
    - Set category identifier for actions
    - Create UNCalendarNotificationTrigger
    - Schedule with UNUserNotificationCenter
```

#### 3. Notification Response Flow
```
User receives notification
    ↓
User press-and-holds (or swipes)
    ↓
Action buttons appear (Yes/No)
    ↓
User taps action
    ↓
UNUserNotificationCenterDelegate.didReceive() called
    ↓
NotificationManagerVM handles response
    ↓
If "Yes":
    - Mark notification as completed
    - Call PickupSchedulerVM.recordBinCompletion()
    - Update bin statistics (streak, completed count)
    - Save to UserDefaults
If "No":
    - Mark notification as missed
    - Call PickupSchedulerVM.recordBinMissed()
    - Reset streak, increment missed count
    - Save to UserDefaults
```

### Performance Optimizations

1. **Lazy Loading**: Views load content on demand
2. **@Published Properties**: Only trigger UI updates when needed
3. **Efficient Data Structures**: Dictionaries for O(1) lookups
4. **Background Processing**: Camera and ML run on background threads
5. **Debouncing**: Prevent excessive notifications scheduling
6. **View Caching**: Reusable SwiftUI components
7. **Async Operations**: Non-blocking UI for network/storage operations

### Error Handling

1. **Camera Errors**: Permission denials, hardware unavailable
2. **Notification Errors**: Permission denials, scheduling failures
3. **ML Errors**: Model loading failures, classification errors
4. **Data Errors**: Encoding/decoding failures, storage errors
5. **User Feedback**: Alerts and error messages for user-facing issues

---

## 🔌 System Extensions

### Notification Categories

#### 1. BIN_REMINDER Category
```swift
Purpose: Remind users about upcoming bin collections
Actions:
- BIN_YES (identifier): "✅ Put Out" (foreground)
- BIN_NO (identifier): "❌ Missed"
Usage: Scheduled 1-24 hours before collection
```

#### 2. WEEKLY_TIP Category
```swift
Purpose: Educational recycling tips
Actions:
- TIP_DISMISS (identifier): "Got it!"
Usage: Scheduled weekly on user-defined day
```

#### 3. TEST_NOTIFICATION Category
```swift
Purpose: Test notification system functionality
Actions:
- TEST_YES (identifier): "✅ Yes, it works!" (foreground)
- TEST_NO (identifier): "❌ Not working"
Usage: Triggered manually by user, delivered in 15 seconds
```

### Delegate Implementations

#### UNUserNotificationCenterDelegate
```swift
Class: NotificationManagerVM

Methods Implemented:
1. userNotificationCenter(_:didReceive:withCompletionHandler:)
   - Handles notification action responses
   - Routes to appropriate handler based on action identifier
   - Updates app state and statistics

2. userNotificationCenter(_:willPresent:withCompletionHandler:)
   - Handles foreground notifications
   - Returns presentation options: [.banner, .sound, .badge]
```

### Widget Extensions (Future Enhancement)

**Planned Widget Types:**
1. **Next Pickup Widget**: Shows upcoming bin collection
2. **Points Widget**: Displays current recycling points
3. **Streak Widget**: Shows active streaks for motivation
4. **Quick Scan**: Deep link to camera scanner

### App Clips (Future Enhancement)

**Planned Use Cases:**
1. **Quick Scan Clip**: Lightweight scanning without full app
2. **Schedule Check Clip**: View bin schedule on the go

---

## 📊 Statistics & Analytics

### Tracked Metrics

#### User Engagement
- App launches per week
- Scans per session
- Notification response rate
- Streak maintenance rate
- Average points per week

#### Recycling Behavior
- Most scanned item types
- Preferred bin collection days
- Notification response time
- Missed collection patterns
- Seasonal variations

#### Performance Metrics
- ML classification accuracy
- Notification delivery success rate
- App crash rate
- Average session duration
- Storage usage

---

## 🔐 Privacy & Security

### Data Collection
- **Local Storage Only**: All data stored on device via UserDefaults
- **No Server Communication**: No data sent to external servers
- **No User Tracking**: No analytics or tracking SDKs
- **Camera Privacy**: Images processed locally, not saved

### Permissions Required
1. **Camera**: Required for waste scanning
2. **Notifications**: Optional but recommended for reminders

### Data Retention
- **User Control**: Clear all data option in settings
- **Automatic Cleanup**: Old notifications removed automatically
- **No Backups**: Data not backed up to iCloud (user can enable)

---

## 🚀 Future Enhancements

### Planned Features
1. **Community Features**
   - Local recycling statistics
   - Neighborhood leaderboards
   - Shared collection schedules

2. **Advanced AI**
   - Multi-item detection
   - Contamination warnings
   - Recycling quality scoring

3. **Integration**
   - Calendar app integration
   - Reminders app sync
   - Widget extensions
   - Apple Watch companion app

4. **Gamification 2.0**
   - Achievements and badges
   - Monthly challenges
   - Reward redemption
   - Social sharing

5. **Educational Content**
   - In-app recycling guides
   - Video tutorials
   - Local facility information
   - Material-specific tips

---

## 🛠️ Development Setup

### Requirements
- Xcode 14.0+
- iOS 16.0+ deployment target
- Swift 5.0+
- CoreML model file

### Build Instructions
```bash
1. Clone repository
2. Open RecycloScan.xcodeproj
3. Select target device/simulator
4. Build and run (⌘R)
```

### Testing
```bash
# Unit Tests
⌘U to run all tests

# UI Tests
Select RecycloScanUITests scheme and run
```

---

## 📄 License

Copyright © 2025 RecycloScan Team
All rights reserved.

---

## 👥 Credits

**Development Team:**
- Kgobi: Pickup Scheduler, Notifications, Statistics
- Yu: Recycling Manager, Points System, Pending Collections
- Ariel: Waste Scanner, Camera Integration, ML Classification
- Tlaitirang: UI/UX Design, Styling, Color Theme

**Technologies:**
- Apple CoreML
- Apple Vision Framework
- SwiftUI
- UserNotifications Framework
- AVFoundation

---

## 📞 Support

For issues, questions, or feature requests:
- GitHub Issues: [Repository Issues Page]
- Email: support@recycloscan.app

---

**Version:** 1.0.0  
**Last Updated:** October 22, 2025  
**Platform:** iOS 16.0+
