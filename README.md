# sbox-crosshair
A semi-complete and configurable crosshair system built for [s&box](https://sbox.facepunch.com/news)

## Installation

Drag the `ui` folder into the `code` folder of your gamemode. Ex. `minimal/code/ui`

## Usage

Add the following to the setup of your main gamemode hud.

```csharp
RootPanel.AddChild<Crosshair>();
```

```csharp
public MinimalHudEntity()
{
  if ( IsClient )
  {
    RootPanel.SetTemplate( "/minimalhud.html" );

    RootPanel.AddChild<ChatBox>();

    RootPanel.AddChild<Crosshair>();
  }
}
```

Call `SetupCrosshair` and optionally provide some `properties`. The `properties` follow a very similar structure to CS:GO.

```csharp
Crosshair.Current?.SetupCrosshair(new Crosshair.Properties(
  true,
  false,
  false,
  25,
  2,
  2,
  -25,
  new Color(0.1f, 1f, 0.3f, 1f)
));
```

Full usage...

```csharp
public MinimalHudEntity()
{
  if ( IsClient )
  {
    RootPanel.SetTemplate( "/minimalhud.html" );

    RootPanel.AddChild<ChatBox>();

    RootPanel.AddChild<Crosshair>().SetupCrosshair(new Crosshair.Properties());
  }
}
```

## Examples

![Example 1 crosshair](https://raw.githubusercontent.com/mzegar/sbox-crosshair/main/examples/1.png)
![Example 2 crosshair](https://raw.githubusercontent.com/mzegar/sbox-crosshair/main/examples/2.png)
![Example 3 crosshair](https://raw.githubusercontent.com/mzegar/sbox-crosshair/main/examples/3.png)
