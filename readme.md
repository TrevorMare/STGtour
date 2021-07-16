# ST GTour - Under Construction

## Welcome Message
Welcome to Sir Trixalot's Guided Tour Service. If you look out your left window you'll see the famous Blazor Beast, On the right you'll see some wanting developers.

This plugin was inspired by all the Angular npm packages that are so freely available for quick starts and not so much for Blazor. Additionally, since 
the .net5 release I have been burning to try it out. So this is my attempt at a contribution to the community and I really hope you find it usefull and saves you some time.

A live [demo](https://www.google.com) can be found here. TODO

## Important Notes
This plugin relies on .net5 and can be ported if you want. The whole idea for me regarding this project was to spend some time on the framework. It might also not have all the features of one of the existing packages but I'm pretty sure it can be extended to do what you want. Another thing I wanted to try was to use the minimum javascript to see how far I can push Blazor.

Additionally, for now this project uses Server Side Rendering and I will see if I can add a WASM demo as well.

# Roll your own
## Build Requirements
To build this project you need to have Satan's tool installed (NodeJs) as this is used for some of the dependencies that's included in the project.

# TLDR

## Installation

- Download with nuget

## Usage
### Register the service in Startup.cs

```c
    using GTour;
    ...
    ...
    public void ConfigureServices(IServiceCollection services)
    {
      ...
      services.UseGTour();
      ...
    }
```

### Add Styles to the _Host.cshtml (optional)

```html
    <link rel="stylesheet" href="_content/GTour/css/styles.css" />
```

### Create a Tour
  
The tour can be included in a separate Razor Component or on the page.

```html
    @using GTour.Components
    <GuidedTour TourId="FormGuidedTour" OverlayEnabled="true">
        <GuidedTourStep Title="My First Step" StepName="firstStep" TourStepSequence="1" ElementSelector="[data-form-firstStep]">
            <span>This is my first step</span>
        </GuidedTourStep>
    </GuidedTour>
```

Set the step target

```html
    <div data-form-firstStep>
        <span>My parent container is the first step target, see my parent wrapper's data attribute corresponding to the ElementSelector of the step?</span>
    </div>
```

### Run tour via service

```c
@code {
  [Inject]
  private GTour.Abstractions.IGTourService GTourService { get; set; }

  private async Task StartTour()
  {
    await GTourService.StartTour("FormGuidedTour");
  }

}
```

# Contributing
We all have some amazing ideas, but it's dependant on what the sand in the glass allows us. So if you have spare and wish to contribute to this project, feel free to do so.

1. Fork the Project
2. Create your Feature Branch (git checkout -b feature/WithKitchenSink)
3. Commit your Changes (git commit -m 'Add some bugs')
4. Push to the Branch (git push origin feature/WithKitchenSink)
5. Open a Pull Request

# Shout-outs
This project uses [popper.js](https://popper.js.org/) to align the tour steps. Kudos

# Holler

Trevor Maré - [trevorm336dev@gmail.com](mailto:trevorm336dev@gmail.com)

Project Link - [GTour](https://github.com/TrevorMare/STGTour)

# License
Distributed under the WTFPL License. See [LICENSE](http://www.wtfpl.net/) for more information.

# Stuff I learned
1. I really liked the Styles and Javascript Isolation that .net has brought us. It really cleans up the host page considerably.
2. I do think some more work can be done on getting npm packages and the projects to play along better, especially since it's "early" days for Blazor and a lot of functionality is still lacking in the UI Interop department.
3. 

