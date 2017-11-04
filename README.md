# StatefulView
An Overlay UIView For Managing UICollectionViews

This small library was created when utilizing the framework [IGListKit](https://github.com/Instagram/IGListKit) for displaying collections.
When adhering to the IGList protocol, there exists a method with the signature:

```swift
func emptyView(for listAdapter: ListAdapter) -> UIView?
```
This is called when no diffable items exists for the UICollectionView. 

When generically loading data, there exists default states:

1. Loading
2. Empty (No Data)
3. Error

This library attempts to simplify the transitions among thesese various state by creating a simple UIView that can handle
the generic states.

## Getting Started

Install the library via [CocoaPods](https://cocoapods.org/) by referencing in your Podfile.
```pod
  pod 'StatefulView'
```
## Simple Example

Create a StatefulView Object:
```swift
var statefulView: StatefulView = StatefulView()
```

### Set Views you would like to display for different states.

#### By class:
```swift
self.statefulView.setAvailableViews(loadingView: LoadingView())
```

#### by XIB name:
```swift
self.statefulView.setAvailableViewsByName(errorView: "ErrorView", emptyView: "EmptyView")
```

### Change states when desired:
```swift
self.statefulView.setState(state: .loading)
```

### Pass in a completion block to be executed when the view is tapped:
```
self.statefulView.setHandlers(loadingView: { print("Loading View Clicked")})
```

## Example 
See the StatefulViewExample project for a brief demo.

## Additional
Feel free to make suggestions or provide feedback regarding the library. Thanks.
