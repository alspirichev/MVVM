# MVVM

**Model–view–viewmodel (MVVM)** is a software architectural pattern.

MVVM facilitates a separation of development of the graphical user interface (**UI**) – be it via a markup language or GUI code – from the development of the **business logic** or back-end logic (the data model). The **view model** of MVVM is a value converter, meaning the view model is responsible for exposing (converting) the data objects from the model in such a way that objects are easily managed and presented. In this respect, the view model is more model than a view and handles most if not all of the view's display logic. The view model may implement a mediator pattern, organizing access to the back-end logic around the set of use cases supported by the view.

## Components of MVVM pattern

![MVVM Pattern](https://upload.wikimedia.org/wikipedia/commons/8/87/MVVMPattern.png)

**ViewModel** takes a central role in the architecture: It takes care of the business logic and talks to both the model and the view. MVMM contains the following components:

* **Model**:   
> Model refers either to a domain model, which represents real state content (an object-oriented approach), or to the data access layer, which represents content (a data-centric approach). Models don’t talk directly to other classes, although they can emit notifications about data changes.

* **View**:  
> As in the MVC and MVP patterns, the view is the structure, layout, and appearance of what a user sees on the screen (UI). Views only notify view controllers about events (just as with MVC).

* **View model**:   
> The view model is an abstraction of the view exposing public properties and commands. Instead of the controller of the MVC pattern, or the presenter of the MVP pattern, MVVM has a binder. In the view model, the binder mediates communication between the view and the data binder. The view model has been described as a state of the data in the model. View Models talk to Models and expose data to the View Controllers.

*View Controllers* only talk to *View Models* and Views as they handle view lifecycle and bind data to UI components.

On OS X, one can use Cocoa bindings, but we don’t have that luxury on iOS. Key-value observation comes to mind, and it does a great job. However, it’s a lot of boilerplate for simple bindings, especially if there are lots of properties to bind to. Instead, I like to use RxSwift, but there’s nothing forcing one to use RxSwift with MVVM. MVVM is a great paradigm that stands on its own and is only made better with a nice binding framework

### Benefits of using this pattern

- MVVM works best with a **binding** mechanism.
- A common issue is stuffing view controllers with code that doesn’t control the **view** *per se*. MVVM tries to solve this problem by grouping the view controller together with the view, and assign its sole responsibility of controlling the view.
- **Reused between platforms**. The view model is completely separated from the presentation layer and, when necessary, can be re used between platforms. You can just replace the view / view controller pair and migrate your app from iOS to macOS or even tvOS.
- **Testability**. Separating the view lifecycle from the business logic makes testing both the view controller and the view model very straightforward.

### Sources
* [Introduction to MVVM (www.objc.io)](https://www.objc.io/issues/13-architecture/mvvm/)
* [Model–view–viewmodel (wiki)](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93viewmodel)
* [RxSwift. Reactive Programming with Swift (book of raywenderlich.com)](https://store.raywenderlich.com/products/rxswift?_ga=2.120608779.2030264741.1503923403-957043677.1495373270)
