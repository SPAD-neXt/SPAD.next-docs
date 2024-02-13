# SPAD Gauges: GaugeSettings

Each SPAD.neXt compatible gauges should contain a GaugeSettings-node to identify the gauge, it's author and some general settings.

Minimal Example:

```
<GaugeSettings GaugeCompatibility="SPAD" GaugeID="!!! INSERT NEW GAUGEID HERE !!!!" PowerMode="AlwaysOn">
	<Author>Your Name here</Author>
	<AuthorId>!! INSERT AUTHORID HERE!!!</AuthorId>
	<Description>General Airliner Gauge</Description>
	<Simulation>MSFS</Simulation>
	<!-- Only if thumbnail provided, else spad will generate one, filename of thumb in 1024 directory
	<Thumbnail>myThumb.png</Thumbnail> 
	-->
</GaugeSettings>
```

GaugeId

Unique Identifier identifying the gauge. It should follow the GUID-Registryformat e.g. "{A8AA15C5-7BB6-4AC6-A558-A88CAFB78729}". To create a GUID you can use this site: [https://www.guidgenerator.com/online-guid-generator.aspx](https://www.guidgenerator.com/online-guid-generator.aspx) (enable at least hyphens)

AuthorId

Your AuthorId. You can get it by sendign the command `!deviceinfo` to teh SPAD.neXt Bot on the community discord.

