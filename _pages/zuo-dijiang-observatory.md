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

.pulsar-facts {
  margin-top: 0.6rem;
  padding-left: 1.1rem;
}

.pulsar-facts li {
  margin-bottom: 0.25rem;
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

    <p>I have been working on this telescope from the ground up: testing the control system, calibrating the pointing, checking the observing chain, and turning it from an instrument on site into something that can actually catch pulsar signals.</p>

    <p>A large part of the work has been building a pulsar observing terminal with SDR hardware and software. I use it to record radio data, handle interference, fold pulsar signals, and turn the result into something students and visitors can actually see and hear.</p>

    <p>For me, this telescope is where classroom astronomy meets real observing: control, pointing, calibration, receiver behavior, radio-frequency interference, and signal processing all become visible.</p>
  </div>

  <figure>
    <img src="/images/njurt/njurtBird.jpeg" alt="4.5-m radio telescope at Nanjing University's Zuo Dijiang Observatory">
    <figcaption>4.5-m radio telescope at Nanjing University's Zuo Dijiang Observatory.</figcaption>
  </figure>
</div>

Detected Pulsar Signals
======

Pulsars are not just objects in textbooks. With radio observations and basic signal processing, their pulses can be detected, folded, and displayed as real astronomical signals.

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
{% assign b1933 = site.static_files | where: "path", "/images/njurt/B1933+16.png" | first %}

<section class="pulsar-detection">
  <div>
    <h3>PSR B0329+54</h3>
    <div class="pulsar-meta">PRESTO prepfold detection</div>
    <p><a href="https://en.wikipedia.org/wiki/PSR_B0329%2B54">B0329+54</a> is a bright northern pulsar, and a friendly first target when checking whether a small radio telescope is really behaving. In this fold, the pulse is already clear enough that the observation feels less like a test and more like a first conversation with the sky.</p>
    <ul class="pulsar-facts">
      <li>Folded period: about 714.52 ms</li>
      <li>DM: about 27.18 pc cm<sup>-3</sup></li>
      <li>Good source for first-light tests and timing-chain checks</li>
    </ul>
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
    <h3>PSR B1933+16</h3>
    <div class="pulsar-meta">PRESTO prepfold detection</div>
    <p><a href="https://arxiv.org/abs/2502.09342">B1933+16</a> is a good check that the telescope pointing, SDR recording chain, and folding pipeline are working together. The pulse is not as effortless as Vela, which makes it a more satisfying engineering test.</p>
    <ul class="pulsar-facts">
      <li>Folded period: about 358.75 ms</li>
      <li>DM: about 158.64 pc cm<sup>-3</sup></li>
      <li>A useful high-DM test source for the NJU 4.5-m setup</li>
    </ul>
  </div>
  <figure>
    {% if b1933 %}
      <img src="/images/njurt/B1933+16.png" alt="PRESTO prepfold detection figure for PSR B1933+16">
    {% else %}
      <div class="signal-placeholder">Add figure: images/njurt/B1933+16.png</div>
    {% endif %}
  </figure>
</section>

<section class="pulsar-detection">
  <div>
    <h3>Crab Pulsar, PSR B0531+21</h3>
    <div class="pulsar-meta">Giant pulses detected using CODD</div>
    <p>The <a href="https://en.wikipedia.org/wiki/Crab_Pulsar">Crab pulsar</a> sits inside the Crab Nebula, the remnant of the historical supernova of 1054. Here I am showing giant pulses: short, bright flashes that are much more dramatic than the average pulse profile.</p>
    <ul class="pulsar-facts">
      <li>Spin period: about 33.4 ms</li>
      <li>DM used in this detection: about 56.71 pc cm<sup>-3</sup></li>
      <li>Giant pulses make the Crab a vivid time-domain source</li>
    </ul>
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
    <p>The <a href="https://en.wikipedia.org/wiki/Vela_Pulsar">Vela pulsar</a> is one of the brightest radio pulsars in the sky. It is also famous for glitches, sudden changes in rotation that make it a classic object for neutron-star interior physics. For this telescope, Vela is the showpiece: bright, clean, and easy to turn into sound.</p>
    <ul class="pulsar-facts">
      <li>Folded period: about 89.43 ms</li>
      <li>DM: about 67.91 pc cm<sup>-3</sup></li>
      <li>Very high signal-to-noise ratio in the NJU 4.5-m fold</li>
    </ul>
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
    <p><a href="https://arxiv.org/abs/1608.01948">B0950+08</a> is a nearby, low-DM pulsar known for strong pulse-to-pulse variability. In this observation it is not visually loud, but folding still pulls the pulse out of the noise. That makes it a nice example of why pulsar searches are patient work.</p>
    <ul class="pulsar-facts">
      <li>Folded period: about 253.09 ms</li>
      <li>DM: about 3 pc cm<sup>-3</sup></li>
      <li>Weak here, but still visible after folding</li>
    </ul>
  </div>
  <figure>
    {% if b0950 %}
      <img src="/images/njurt/B0950+08.png" alt="Folded detection figure for weak pulsar PSR B0950+08">
    {% else %}
      <div class="signal-placeholder">Add figure: images/njurt/B0950+08.png</div>
    {% endif %}
  </figure>
</section>
