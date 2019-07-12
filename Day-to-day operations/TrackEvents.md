# Track some events

You have implemented your feature but you need data to see how the users behave with it.

## Prerequisite

* The analytics events should be specified in your Jira ticket. If it’s not the case, ask your PM.

## Steps

### Tracking the user is on a particular screen

* Rider - AppScreen.swift
* Driver - AnalyticsScreens.swift

1. Depending on the app, you want to add a case to the screens enum and set the `name` and `properties` computed properties for it.

For example :

```swift
enum Screens: ScreenProtocol {
  case home

  var name: String {
    switch self {
    case .home:
      return "Home"
    }
  }

  var properties: [String: Any]? {
    switch self {
    case .home:
      return nil
    }
  }
}
```

2. Once it’s done, you can now use the `analyticsTracker` dependency to track the screen `dependencies.analyticsTracker.track(screen: Screens.home)`

### Tracking a user event

* Rider - AppEvent.swift
* Driver - AnalyticsEvents.swift

1. Depending on the app, you want to add a case to the events enum and set the `name` and `properties` computed properties for it.

For example :

```swift
enum Events: EventProtocol {
  case orderARideTap

  var name: String {
    switch self {
    case .orderARideTap:
      return "order_a_ride_tap"
    }
  }

  var properties: [String: Any]? {
    switch self {
    case .home:
      return nil
    }
  }
}
```

2. Once it’s done, you can now use the `analyticsTracker` dependency to track the event `dependencies.analyticsTracker.track(event: Events. orderARideTap)`
