<!--- To help us fix your issue, please provide the information in the below template. -->
<!--- Note: There is often little we can do without a minimal reproducible sample of the issue, so please provide that in a **standalone git repository** and link it here. -->
<!---  Please only file bugs verified on latest version of MvvmCross and STABLE Xamarin tools --> 

### Steps to reproduce :scroll:

1. Add new project for Xamarin.ios and add mvvmcross nuget package

2. Make the changes in the AppDelegate file 
public override bool FinishedLaunching(UIApplication apps, NSDictionary Options)
{
			Window = new UIWindow(UIScreen.MainScreen.Bounds);
			var setup = new Setup(this, Window);
      setup.Initialize();
      var startup = Mvx.Resolve<IMvxAppStart>();
      startup.Start();
      Window.MakeKeyAndVisible();
			return true;
}

3. Run the application on simulator iphone 7 plus


### Expected behavior :thinking:
Application have to start the initial screen of the Application 

### Actual behavior :bug:
It raises the Exception on line --> setup.Initialize();
Exception: System.TypeInitializationException has been thrown
The type initializer for 'MvvmCross.Core.Platform.LogProviders.ConsoleLogProvider' threw an exception.

### Configuration :wrench:

**Version:** 
core: .NET standard 2.0
app : Xamarin.ios

**Platform:** 
- [*] :iphone: iOS
- [] :robot: Android
- [ ] :checkered_flag: WPF
- [ ] :earth_americas: UWP
- [ ] :apple: MacOS
- [ ] :tv: tvOS
- [ ] :monkey: Xamarin.Forms
