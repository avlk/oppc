# Method of measurement

My original idea was around making a _continuous_ series of photos of a section of a laminar flow of air containing pollen particles. Pollen particles should be illuminated by a strong light source in otherwise dark ambient conditions so that they appear as light blobs in the dark to the camera. 

I had my master's thesis around detecting pathologic blood cells in the blood sample by processing the microphotographs, first detecting cells and their form/color, and then processing with algorithms. That was quite successful. So I want to use the same method on pollen - detect single pollen particles in the air and then classify them by size, form, etc.

Processing passing air requires no obvious spares, so it should be [low maintenance](project_goals.md#maintainability). Of course, some periodic cleaning of the insides from dust and pollen and changing coarse air filters (blocking poplar fluff and alike) may be required yearly or 2-3 per year. 

## Streaming approach

The simplest way would be just to make a series of photos with equal intervals and detect particles in the photos.

![Streaming approach](assets/images/method-streaming-approach.png)

In a picture, a laminar airflow is passing with a constant speed, **V**(mm), through the camera **DOF**(mm) - depth of field zone. DOF is illuminated by a powerful light source - it should be powerful enough to keep camera exposure time short. To photograph all passing air we need V/DOF frames per second - this is one of our constraints.

A camera with sensor size __Xs\*Ys__(mm), pixel pitch **Pp**(um) - pixels are usually rectangular, and sensor resolution __X\*Y__=(Xs\*1000/Pp, Ys\*1000/Pp), needs to see some area across the beam of the light source. 

A lens provides the DOF for the camera at some focusing distance. 
We want the picture of any pollen particle to be no less than some **P** pixels in "diameter". That means, that the minimal magnification of the lens+camera system can be defined through the minimal [detectable pollen size](project_goals.md#objective-technical-data), Xpollen(pixels), as **Mmin**=(Xpollen/P)/Pp. 

Let's calculate Mmin. At the time of writing the minimal pollen size was 20um. For a pixel pitch of 2um and desirable pollen size of 8x8 pixels, Mmin=(20/8)/2=1.25. 

To be continued...



