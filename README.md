# s3e10-pulsar-prediction
Binary classification of Pulsars

## Background

**Below text and images from [here](https://as595.github.io/classification/).**

Pulsars are “pulsating radio sources”, now known to be caused by rapidly rotating neutron stars. Neutron stars are the relics of dead massive stars, they’re small and extremely dense - something the same mass as the Sun crammed into a radius roughly the same as the M25 motorway around London. 

A characteristic property of pulsars are the periodic bursts of emission produced by their radio emitting jets. As the pulsar rotates, the direction of this emission also rotates and astronomers see a pulse of radio emission each time one of the jets points towards the Earth.

Identifying them in the data streams from radio telescopes is not trivial. There are lots of man-made sources of radio frequency interference that can mimic the signals from pulsars. Classifying candidate data samples as pulsar or not pulsar is serious business.

In order to classify a data sample as a pulsar or not a pulsar, we need to be able to extract some information on the data sample that can characterise its class. The individual bursts of emission from a pulsar (i.e. the pulses) do not have a constant shape or amplitude, so individually they’re not very useful for uniquely identifying a pulsar.

Because the individual pulses are all different, astronomers stack them up and create an average integrated pulse profile to characterise a particular pulsar:

![pulses](https://github.com/jfblanchard/s3e10-pulsar-prediction/blob/main/images/pulsar%20stacking.gif)

Additionally the pulse will arrive at different times across different radio frequencies. The delay from frequency to frequency is caused by the ionised inter-stellar medium and is known as the dispersion. Astronomers fit for the shape of the delay in order to compensate for its effect, but there’s always an uncertainty associated with the fit. That is expressed in the DM-SNR (“dispersion-measure-signal-to-noise-ratio”) curve.

When you put these two curves together it means that for each pulsar candidate there are eight numerical characteristic features that can be extracted as standard: four from the integrated pulse profile and four from the DM-SNR curve.
