# OPPC Project Goals

## Vision of result

A network of pollen-counting devices covering urban and rural areas provides people with actual information on pollen concentration so that they can be safe and live in comfort.

## High-level definition

- The device runs in an automatic mode and delivers pollen concentrations to the cloud.
- It can detect pollen particles in the air and distinguish them from non-pollen particles (dust, fiber, etc).
- It can classify pollen into several species and count the concentration of these species in the air.
- It is typically mounted on an outer wall or an open balcony of a house, and connected to a home electrical supply and WiFi.
- It is assembled and maintained by an enthusiast user but requires low maintenance once installed.

## Particular goals

### Practical vs. Scientific

*The goal of the project is to deliver practically viable results rather than scientific results. It will trade cost vs. scientific viability to achieve greater coverage while still providing value for allergic persons.*

Scientific devices usually aim to classify pollen into 20+ species, cost $$$, and require very specific hardware for the automatic measurement. They also have metrologically sound results, although the error could be in the 10% range, which is acceptable.

The most common type of pollen sampling device is a Burkard trap, which draws in the air and the particles drawn are then stuck to a slowly rolling sticky tape. This tape is then inspected by a human operator. This is considered a golden standard and it can distinguish a wide variety of pollen species and between pollen and non-pollen particles.

Automated counters tend to challenge the Burkard trap on its field and provide comparable results. So that they can also be used for science, probably.

Automated classification of pollen is hard because those particles are very small (between 10-100um, typically 20-50um), have shape similarities, and are mostly done with the same material, which makes some species hard to distinguish from others. Therefore, some lasers, optical sensors, and spectrometers are used to provide good live results or the sticky tape method is automated with microscopic cameras. Both methods challenge manual counting but provide too accurate results for quite a large amount of money.

In real life we don't want to classify, e.g. Lily pollen from the Birch pollen, or Rye pollen from the Hazelnut pollen. And here is the difference between a *practical* and a scientific approach.

- Groups of species bloom at different times in a particular region. Therefore, a *practical* device can use location and time to distinguish between species in such groups.
- Most allergic people are highly sensitive to one or several pollen types in the place where they live, and it is *practically* useful to detect 2-5 airborne allergens at each moment. For example, in northern Europe, the season is usually started with Hazelnut, and Alder, followed by Birch, Oak, Maple, Ash, Willow, and so on. Not each species is present in each region, and not each species creates a problem for allergic people as well. 

From a _practical_ side, it is already viable to count and distinguish just 2 pollen types in the early spring, about 5 types of pollen throughout the whole spring - in a particular region. This would increase the quality of life for a lot of people.

Even in a case where it wouldn't be possible to distinguish Hazelnut and Adler in the early spring (due to their similarity), providing a combined count would deliver a *practical* result: in many regions, these species bloom at the same time and with correlating concentrations, so if you are sensible to any of these, you have to take all your precautions anyway.

### Typical user

A typical user of the device is an allergic person or a member of her family. He may be a DIY enthusiast or know someone who is a DIY-er and can assemble and install such a device. The typical user is ready to cover the associated costs of the device and installation since it will not only provide direct value to her or her family by measuring pollen concentrations directly at her house but also provide value to a greater population of the area.

### Area coverage

In highly-populated urban areas, the goal is to have 2-3 devices installed per 1 Million city, or 5+ devices for a larger city. As there are not so many forests or meadows inside such areas, and the areas are dense, the pollen concentration would be quite similar in a stretch of 10km and more around the place and the data provided by a network of several devices would be already representative.

For rural areas and small towns, the goal is to have at least one device per 100km. This goal is harder to achieve due to a generally lower income and less populational density in such areas. As an upside - these areas are generally covered by the forests and fields of similar types throughout a region, and pollen tends to travel tens and hundreds of kilometers, so the measurement results done 50km from your house may be still very representative.

### Cost of the device

The cost of the device and installation is planned to be below $2000. It is a high figure, but it creates some headroom for creating a device from good components, allowing less price vs. performance tradeoffs. However, it is much lower than that of commercial devices capable of fully scientific measurements. For 

With a $2000 price tag, this is not going to be a thing everyone buys for fun, but people spend such an amount of money on their hobbies. Drones, cameras, and quad ATVs are bought just for fun in the same price range. Considering the target coverage area and a generally high density of allergic people, there should be a person who can afford such a device for her advantage and the advantage of the people around.

### Data collection

Data is to be collected in the cloud. Devices are to be managed by IoT service (probably, AWS IoT Core). Collected data from all devices can then be visualized with Grafana.

### Maintainability

The device should not require daily maintenance.

No commodities should be required that are supplied on a daily, weekly, or even monthly basis, like rolls of sticky tape.

The device is going to be maintained by a person with low skills and with simple tools. These skills and tools should be lower than those required to create and assemble the device:
- Sometimes the device can be ordered from a skilled DIY-er by an enthusiast.
- This also creates a normal living tempo for any person owning the device, especially in a pollen season.

It is going to require some maintenance 1-3 times per year, with operations like:
- Replacing 3D-printed pre-made parts, or off-the-shelf parts
- Cleaning internal structures with wet wipes or compressed air

The whole cycle of maintenance is to be less than 3 hours.

## Objective technical data

- Size of detectable pollen: 20-100um
- Detectable pollen concentration: 100-10000 per cubic meter
 