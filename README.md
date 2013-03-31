# CLFContainerViewController

CLFContainerViewController is a UIViewController subclass that is designed to make the creation of custom container view controllers much easier.

When subclassing CLFContainerViewController to create your own custom container, you do not have to worry about managing the view controller hierarchy, or the view hierarchy. You also do not have to worry about forwarding appearance transition methods (like viewWillAppear, viewDidAppear, etc.) to your child view controllers. These details will all be handled by CLFContainerViewController, and will work properly even when the container itself is transitioned away from (so you are free to include containers in other containers without having to worry about how the transitions will be affected).

If your container is inside of a UINavigationController, the navigationItem properties will change accordingly as your container transitions between child view controllers.

You are also given a powerful method for transitioning between view controllers in switchToViewController:animated:preAnimationSetup:animations:animationDurations:animationOptions:completionBlock:.

With this class, you can create container view controllers who's children occupy the entire bounds of the container. For example, your subclass could mimic a UINavigationController, a UITabBarController, or a UIPageViewController, though you are certainly not limited to recreating already existing containers.

This class, however, does not give you the ability to create a container view controller that displays multiple view controllers in different portions of the screen, like a UISplitViewController would.

## Subclassing the Subclasses

Two useful subclasses are included for you to further subclass, or to examine for examples of how to subclass CLFContainerViewController.

CLFStackContainerViewController implements a container view controller that functions as a stack with push and pop methods for adding and
removing view controllers.

CLFTabbedContainerViewController implements a container view controller that functions similarly to a UITabBarController, although it does not include any UI for a tab bar (you could further implement such UI in your own subclass).

## Example Project

The example project further demonstrates subclassing CLFContainerViewController. With the exception of the UINavigationController that is used solely for its UINavigationBar, all of the containers in the example project are subclasses of CLFContainerViewController.

The MainViewController is a subclass of CLFTabbedContainerViewController, and adds the segmented control for switching between view controllers. It also manages the setup of the other containers.

The StackWithPopButtonViewController is a subclass of CLFStackContainerViewController, and adds a "Pop" button when you have view controllers pushed onto the stack.

The WobbleViewController is just a subclass of CLFContainerViewController. It's not a very practical container view controller in itself, but it does demonstrate the use of multiple animation blocks in a transition.