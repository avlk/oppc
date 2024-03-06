# Method of measurement

My original idea was around making a _continuous_ series of photos of a section of a laminar flow of air containing pollen particles. Pollen particles should be illuminated by a strong light source in otherwise dark ambient conditions so that they appear as light blobs in the dark to the camera. 

I had my master's thesis around detecting pathologic blood cells in the blood sample by processing the microphotographs, first detecting cells and their form/color, and then processing with algorithms. That was quite successful. So I want to use the same method on pollen - detect single pollen particles in the air and then classify them by size, form, etc.

Processing passing air requires no obvious spares, so it should be [low maintenance](project_goals.md#maintainability). Of course, some periodic cleaning of the insides from dust and pollen and changing coarse air filters (blocking poplar fluff and alike) may be required yearly or 2-3 per year. 


## Streaming approach

The simplest way would be just to make a series of photos with equal intervals and detect particles in the photos.

![Streaming approach](assets/images/method-streaming-approach.png)

In a picture, a laminar airflow is passing with a constant speed, **V**(mm), through the camera **DOF**(mm) - depth of field zone. DOF is illuminated by a powerful light source - it should be powerful enough to keep camera exposure time short. To photograph all passing air we need **FPS**=V/DOF frames per second.

A camera with sensor size __Xs\*Ys__(mm), pixel pitch **Pp**(um) - pixels are usually rectangular, and sensor resolution __X\*Y__=(Xs\*1000/Pp, Ys\*1000/Pp), needs to see some area across the beam of the light source - camera FOV.

A lens provides the DOF for the camera at some focusing distance. At a minimal focusing distance, MFD(mm), the lens provides the best magnification, but the smallest FOV.

### Processed air volume

The volume that is processed in a single shot is defined as the camera+lend FOV=HFOV\*VFOV (field of view, mm\*mm) area multiplied by the DOF. As we are going to photograph something small, it is already obvious that the size of a FOV would possibly be in the range of millimeters. The DOF would also be on a millimeter scale (OK, maybe you don't know yet, but we'll see it soon). 

That's what it practically means: if we have a FOV of, say, 8*\6 mm and a DOF of 2mm, the camera+lens system shoots 8\*6\*2=96 cubic mm. of air in one shot. At 30FPS it will process 30\*96=2880 cubic mm and in one hour - 2880*3600=10.368 million cubic mm, or just 10.368 liters of air - that's only 1% of a cubic meter. We want to [detect between 100 and 10000 particles per cubic meter](project_goals.md#objective-technical-data), and at the lowest concentration, the system would see just one pollen particle in an hour. Rather it would see 24 particles in 24 hours and then we say - yes, the pollen concentration is somewhere around 100/cubic.m. The system would work but would have a very slow response, which is unwanted.

If we can design a system to process 40 liters per hour, it would detect 16 samples in 4 hours and it could then say, in practical means, that the concentration is around 100/cubic.m. just in 4 hours - that's much better. 

> Of course, by measuring 16 particles in 4 hours we can's precisely say it is 100 particles per cubic meter - we can just assume that the real average concentration over these 4 hours lies in some range of values, say, 70..130, with some probability, like 95%. But that's scientific results. For [practical results](project_goals.md#practical-vs-scientific) this is fine: this concentration is rather small to cause any allergy, and for most allergic people such a value is just an indicator that the pollen season is starting. And at higher concentrations per cubic meter, when it matters more if it is 5000 or 7000 we automatically get better results by counting more particles per hour.

Liters/hour is a major practical design constraint for the system. We would optimize the system to improve this value. Let's define some practical values:

| l/h of processed air | Applicability
| ------- | -------
| < 20    | Poor
| 20..40  | Acceptable
| 40..100 | Good
| > 100   | Excellent

It's still a question if we could ever achieve excellent results.

### Camera resolution and magnification

We want the picture of any pollen particle to be no less than some **P** pixels in "diameter". That means, that the minimal magnification of the lens+camera system can be defined through the minimal [detectable pollen size](project_goals.md#objective-technical-data), Xpollen(pixels), as **Mmin**=(Xpollen/P)/Pp. 

Let's calculate sample Mmin. At the time of writing the minimal pollen size was 20um. For a pixel pitch of 2um and desirable pollen size of 8x8 pixels, Mmin=(20/8)/2=1.25. 

To be continued...



