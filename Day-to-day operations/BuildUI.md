# Build the UI

You now have a feature to work on that requires to build the UI in the app.

## Prerequisite

* Access to Zeplin and to the design models.

## Steps

We don’t use storyboards at Kapten but instead build our UI with code and SnapKit which is really easy to grasp and it gives us the ability to review the UI code in our code reviews.

Because we are working with MVVM, our UI code is located in view controllers and it usually follows this pattern :

```swift
import SnapKit
import UIKit

final class SomeViewController: UIViewController {
  // MARK: - Properties

  private let someView: UIView

  // MARK: - Initializers

  init(viewModel: SomeViewModelIO) {
    self.someView = UIView()
  }

  // MARK: - Lifecycle

  override func viewDidLoad() {
    super.viewDidLoad()
    setup()
    bind()
  }

  // MARK: - Setup

  private func setup() {
    view.addSubview(someView)
    setupSomeView()
  }

  private func setupSomeView() {
    // This is how you setup your view's constraints with SnapKit
    someView.snp.makeConstraints {
      $0.edges.equalToSuperView()
    }
  }

  // MARK: - Binding

  private func bind() {
    // This is where you bind your view model
  }
}
```

As you can see, we setup our views in separate private functions so it’s easier to focus on a particular view.

For details about SnapKit or specific views such as `UITableView` or `UITextField`, we suggest to look at existing code to see how it’s done.
