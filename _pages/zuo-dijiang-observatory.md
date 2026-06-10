---
layout: archive
title: "4.5-m Radio Telescope at NJU"
permalink: /zuo-dijiang-observatory/
author_profile: true
---

<style>
.page__title {
  display: none;
}

.njurt-intro {
  display: grid;
  grid-template-columns: minmax(0, 1.15fr) minmax(260px, 0.85fr);
  gap: 1.5rem;
  align-items: start;
  margin-bottom: 1.5rem;
}

.njurt-intro h1 {
  margin-top: 0;
}

.njurt-intro figure {
  margin: 0;
}

.njurt-intro img {
  width: 100%;
  max-width: 100%;
  border-radius: 4px;
}

.njurt-intro figcaption {
  color: #666;
  font-size: 0.85em;
  margin-top: 0.4rem;
}

.pulsar-detection {
  display: grid;
  grid-template-columns: minmax(0, 0.95fr) minmax(280px, 1.05fr);
  gap: 1.25rem;
  align-items: start;
  border-top: 1px solid #e5e5e5;
  padding-top: 1.25rem;
  margin-top: 1.25rem;
}

.pulsar-detection h3 {
  margin-top: 0;
}

.pulsar-meta {
  color: #666;
  font-size: 0.9em;
  margin-bottom: 0.5rem;
}

.pulsar-detection figure {
  margin: 0;
}

.pulsar-detection img,
.pulse-media video,
.pulse-media audio {
  width: 100%;
  max-width: 100%;
}

.signal-placeholder {
  align-items: center;
  border: 1px dashed #bbb;
  border-radius: 4px;
  color: #666;
  display: flex;
  font-size: 0.9em;
  justify-content: center;
  min-height: 180px;
  padding: 1rem;
  text-align: center;
}

.pulse-media {
  display: grid;
  grid-template-columns: minmax(0, 1fr);
  gap: 1.25rem;
}

@media (max-width: 760px) {
  .njurt-intro,
  .pulsar-detection,
  .pulse-media {
    grid-template-columns: 1fr;
  }
}
</style>

<div class="njurt-intro">
  <div>
    <h1>4.5-m Radio Telescope at NJU</h1>

    <p>Nanjing University's Zuo Dijiang (左涤江) Observatory hosts a 4.5-m radio telescope that provides a hands-on platform for radio-astronomy observing, pulsar signal reception, data acquisition, and public education.</p>

    <p>I am involved in observing practice and outreach activities with this telescope. The goal is to connect the physics of neutron stars with real radio signals: from pointing a small radio telescope and collecting data, to understanding how periodic pulsar signals can be detected and interpreted.</p>

    <p>The 4.5-m radio telescope is especially useful for teaching and demonstration because it makes the full observing chain visible. Students and visitors can follow how a radio signal enters the antenna, passes through the receiver and data-acquisition system, and becomes a time series that can be searched for periodic or transient signals.</p>

    <p>This platform is also a bridge between classroom astronomy and research practice. It introduces the practical constraints of radio observations, including antenna pointing, receiver sensitivity, radio-frequency interference, calibration, and signal processing.</p>
  </div>

  <figure>
    <img src="/images/njurt/njurtBird.jpeg" alt="4.5-m radio telescope at Nanjing University's Zuo Dijiang Observatory">
    <figcaption>4.5-m radio telescope at Nanjing University's Zuo Dijiang Observatory.</figcaption>
  </figure>
</div>

Detected Pulsar Signals
======

One focus of my outreach material is to show that pulsars are not just abstract objects in textbooks. With radio observations and basic signal processing, their pulses can be detected, folded, and displayed as real astronomical signals.

Pulse Playback
======

This short clip turns one of our Vela pulsar detections into sound. The regular ticking is the pulsar signal itself, folded into something you can see and hear rather than only inspect in a diagnostic plot.

{% assign pulse_video = site.static_files | where: "path", "/images/njurt/velaNJURT.mp4" | first %}

<div class="pulse-media">
  <div>
    {% if pulse_video %}
      <video controls preload="metadata">
        <source src="/images/njurt/velaNJURT.mp4" type="video/mp4">
      </video>
    {% else %}
      <div class="signal-placeholder">Optional video: images/njurt/velaNJURT.mp4</div>
    {% endif %}
  </div>
</div>

{% assign b0329 = site.static_files | where: "path", "/images/njurt/B0329_HighSN.png" | first %}
{% assign crab = site.static_files | where: "path", "/images/njurt/crabGP.png" | first %}
{% assign vela = site.static_files | where: "path", "/images/njurt/B0833-45_prepfold.png" | first %}
{% assign b0950 = site.static_files | where: "path", "/images/njurt/B0950+08.png" | first %}

<section class="pulsar-detection">
  <div>
    <h3>PSR B0329+54</h3>
    <div class="pulsar-meta">PRESTO prepfold detection</div>
    <p>B0329+54 is a bright, classic radio pulsar and a good demonstration target for pulsar observing. Its folded profile shows how a weak periodic signal becomes clear after many rotations are added together in phase.</p>
  </div>
  <figure>
    {% if b0329 %}
      <img src="/images/njurt/B0329_HighSN.png" alt="PRESTO prepfold detection figure for PSR B0329+54">
    {% else %}
      <div class="signal-placeholder">Add figure: images/njurt/B0329_HighSN.png</div>
    {% endif %}
  </figure>
</section>

<section class="pulsar-detection">
  <div>
    <h3>Crab Pulsar, PSR B0531+21</h3>
    <div class="pulsar-meta">Giant pulses detected using CODD</div>
    <p>The Crab pulsar is a young neutron star in the Crab Nebula. Its giant pulses are short, bright radio bursts that make it especially useful for showing the time-domain nature of pulsar emission.</p>
  </div>
  <figure>
    {% if crab %}
      <img src="/images/njurt/crabGP.png" alt="Detected giant pulses from the Crab pulsar PSR B0531+21">
    {% else %}
      <div class="signal-placeholder">Add figure: images/njurt/crabGP.png</div>
    {% endif %}
  </figure>
</section>

<section class="pulsar-detection">
  <div>
    <h3>Vela Pulsar, PSR B0833-45</h3>
    <div class="pulsar-meta">PRESTO prepfold detection with very high signal-to-noise ratio</div>
    <p>The Vela pulsar is one of the brightest radio pulsars in the sky. In a folded observation, its pulse profile can appear with extremely high signal-to-noise ratio, making it a striking example of pulsar periodicity.</p>
  </div>
  <figure>
    {% if vela %}
      <img src="/images/njurt/B0833-45_prepfold.png" alt="PRESTO prepfold detection figure for the Vela pulsar PSR B0833-45">
    {% else %}
      <div class="signal-placeholder">Add figure: images/njurt/B0833-45_prepfold.png</div>
    {% endif %}
  </figure>
</section>

<section class="pulsar-detection">
  <div>
    <h3>PSR B0950+08</h3>
    <div class="pulsar-meta">Weak pulsar visible in a folded profile</div>
    <p>B0950+08 is weaker in these observations, but its signal can still become visible after folding. It is a useful example because it shows why pulsar searches rely on coherent accumulation rather than a single obvious pulse.</p>
  </div>
  <figure>
    {% if b0950 %}
      <img src="/images/njurt/B0950+08.png" alt="Folded detection figure for weak pulsar PSR B0950+08">
    {% else %}
      <div class="signal-placeholder">Add figure: images/njurt/B0950+08.png</div>
    {% endif %}
  </figure>
</section>

The observing workflow includes:

* understanding the target pulsar and observing frequency
* pointing and tracking with the radio telescope
* recording radio data as a time series
* removing or identifying radio-frequency interference
* searching for periodic signals
* folding the data to recover an average pulse profile

Observing Practice
======

The telescope can support compact but complete observing exercises. These exercises are designed to help students understand both the astronomical source and the instrument:

* antenna pointing and basic telescope operation
* radio data acquisition and time-domain signal recording
* pulsar periodicity searches and folded pulse profiles
* simple signal-to-noise estimates
* comparison between real observations and simulated pulsar data

Outreach and Education
======

The 4.5-m radio telescope provides a vivid way to introduce radio astronomy to a broad audience. In public talks and teaching material, I use pulsars as a central example because they connect many ideas at once: stellar evolution, neutron-star physics, precision timing, the interstellar medium, and signal processing.

This work is part of my broader interest in making compact-object astrophysics more tangible. A small radio telescope cannot replace large facilities such as FAST or the Green Bank Telescope, but it can show the essential logic of radio observing in a direct and memorable way.
