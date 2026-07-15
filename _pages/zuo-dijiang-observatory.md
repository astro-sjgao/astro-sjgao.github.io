---
layout: archive
title: "NJU 4.5-m Radio Telescope"
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
    <h1>NJU 4.5-m Radio Telescope</h1>

    <p>Nanjing University's Zuo Dijiang (左涤江) Observatory hosts a 4.5-m radio telescope. It is a hands-on platform for radio astronomy, receiving pulsar signals, data acquisition, and public education.</p>

    <p>I have worked on this telescope from the ground up: testing the control system, calibrating the pointing, checking the observing chain, and turning it from an instrument on site into something that can actually catch pulsar signals.</p>

    <p>A large part of the work has been building a pulsar observing terminal with SDR hardware (ANTSDR U220, 56 Msps) and pulsar software, including <a href="https://github.com/scottransom/presto">PRESTO</a>, <a href="https://dspsr.sourceforge.net/">DSPSR</a>, <a href="https://github.com/tftelkamp/vrt-iq-tools">vrt-iq-tools</a>, <a href="https://psrchive.sourceforge.net/">PSRCHIVE</a>, <a href="https://psrdada.sourceforge.net/">PSRDADA</a>, and <a href="https://sourceforge.net/projects/tempo2/">TEMPO2</a>. I use this setup to record radio data, handle interference, fold pulsar signals, and turn the results into something students and visitors can actually see and hear.</p>

    <p>This telescope is where classroom astronomy meets real observing: control, pointing, calibration, receiver behavior, radio-frequency interference, and signal processing all become visible.</p>
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

This short clip turns one of our Vela pulsar detections into sound. The regular ticking is the pulsar signal itself. It is nice to hear the signal, not just look at it in a plot.

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
{% assign b0628 = site.static_files | where: "path", "/images/njurt/B0628-28.png" | first %}
{% assign crab = site.static_files | where: "path", "/images/njurt/crabGP.png" | first %}
{% assign vela = site.static_files | where: "path", "/images/njurt/B0833-45_prepfold.png" | first %}
{% assign b0950 = site.static_files | where: "path", "/images/njurt/B0950+08.png" | first %}
{% assign b1641 = site.static_files | where: "path", "/images/njurt/B1641-45.png" | first %}
{% assign b1933 = site.static_files | where: "path", "/images/njurt/B1933+16.png" | first %}
{% assign j0437 = site.static_files | where: "path", "/images/njurt/J0437-4715.png" | first %}

<section class="pulsar-detection">
  <div>
    <h3>PSR B0329+54</h3>
    <div class="pulsar-meta">PRESTO prepfold detection</div>
    <p><a href="https://en.wikipedia.org/wiki/PSR_B0329%2B54">B0329+54</a> is a bright pulsar and a good first target for a small radio telescope. The signal is clear after folding, so it is very useful when checking whether the telescope and software are working.</p>
    <ul class="pulsar-facts">
      <li>Folded period: about 714.52 ms</li>
      <li>DM: about 27.18 pc cm<sup>-3</sup></li>
      <li>A good source for first-light tests</li>
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
    <h3>PSR B0628-28</h3>
    <div class="pulsar-meta">PRESTO prepfold detection</div>
    <p>B0628-28 is a slow pulsar in this small sample. Its period is longer than one second, so the pulses are easy to imagine as a steady beat. This makes it a good source for showing what folding does.</p>
    <ul class="pulsar-facts">
      <li>Folded period: about 1244.43 ms</li>
      <li>DM: about 34.27 pc cm<sup>-3</sup></li>
      <li>A clear slow-pulsar example</li>
    </ul>
  </div>
  <figure>
    {% if b0628 %}
      <img src="/images/njurt/B0628-28.png" alt="PRESTO prepfold detection figure for PSR B0628-28">
    {% else %}
      <div class="signal-placeholder">Add figure: images/njurt/B0628-28.png</div>
    {% endif %}
  </figure>
</section>

<section class="pulsar-detection">
  <div>
    <h3>PSR B1933+16</h3>
    <div class="pulsar-meta">PRESTO prepfold detection</div>
    <p><a href="https://arxiv.org/abs/2502.09342">B1933+16</a> is a good check for the telescope pointing and SDR data path. The signal is weaker than Vela, but it still comes out after folding, which is exactly what we want to see.</p>
    <ul class="pulsar-facts">
      <li>Folded period: about 358.75 ms</li>
      <li>DM: about 158.64 pc cm<sup>-3</sup></li>
      <li>A useful higher-DM test source</li>
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
    <h3>PSR B1641-45</h3>
    <div class="pulsar-meta">PRESTO prepfold detection</div>
    <p><a href="https://www.atnf.csiro.au/research/pulsar/psrcat/proc_form.php?Name=B1641-45&amp;submit=Table">B1641-45</a> is a bright southern pulsar. Its DM is much larger than the nearby pulsars on this page, so the radio signal has crossed a lot more free electrons before reaching us.</p>
    <ul class="pulsar-facts">
      <li>Folded period: about 455.09 ms</li>
      <li>DM: about 479.29 pc cm<sup>-3</sup></li>
      <li>A strong high-DM test source</li>
    </ul>
  </div>
  <figure>
    {% if b1641 %}
      <img src="/images/njurt/B1641-45.png" alt="PRESTO prepfold detection figure for PSR B1641-45">
    {% else %}
      <div class="signal-placeholder">Add figure: images/njurt/B1641-45.png</div>
    {% endif %}
  </figure>
</section>

<section class="pulsar-detection">
  <div>
    <h3>Crab Pulsar, PSR B0531+21</h3>
    <div class="pulsar-meta">Giant pulses detected using CODD</div>
    <p>The <a href="https://en.wikipedia.org/wiki/Crab_Pulsar">Crab pulsar</a> is in the Crab Nebula, which came from the supernova seen in 1054. Here I show giant pulses: very short and bright radio flashes from the pulsar. These pulses were captured with a real-time coherent-dedispersion pipeline running on a GPU.</p>
    <ul class="pulsar-facts">
      <li>Spin period: about 33.4 ms</li>
      <li>DM used in this detection: about 56.71 pc cm<sup>-3</sup></li>
      <li>Giant pulses can last from nanoseconds to microseconds and can reach flux densities of about MJy.</li>
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
    <div class="pulsar-meta">PRESTO prepfold detection, very strong signal</div>
    <p>The <a href="https://en.wikipedia.org/wiki/Vela_Pulsar">Vela pulsar</a> is one of the brightest radio pulsars in the sky. For our telescope, it is the best showpiece: the pulse is strong, clean, and easy to turn into sound.</p>
    <ul class="pulsar-facts">
      <li>Folded period: about 89.43 ms</li>
      <li>DM: about 67.91 pc cm<sup>-3</sup></li>
      <li>Very strong in this observation</li>
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
    <h3>PSR J0437-4715</h3>
    <div class="pulsar-meta">PRESTO prepfold detection of a millisecond pulsar</div>
    <p><a href="https://en.wikipedia.org/wiki/PSR_J0437%E2%88%924715">J0437-4715</a> is a nearby millisecond pulsar in a binary system. It spins very fast, about 174 times each second. Catching this kind of signal is a nice test of timing, folding, and the whole observing chain.</p>
    <ul class="pulsar-facts">
      <li>Folded period: about 5.76 ms</li>
      <li>DM: about 2.66 pc cm<sup>-3</sup></li>
      <li>A fast nearby millisecond pulsar in a binary system, one of the kinds of systems I study</li>
    </ul>
  </div>
  <figure>
    {% if j0437 %}
      <img src="/images/njurt/J0437-4715.png" alt="PRESTO prepfold detection figure for PSR J0437-4715">
    {% else %}
      <div class="signal-placeholder">Add figure: images/njurt/J0437-4715.png</div>
    {% endif %}
  </figure>
</section>

<section class="pulsar-detection">
  <div>
    <h3>PSR B0950+08</h3>
    <div class="pulsar-meta">Weak pulsar visible in a folded profile</div>
    <p><a href="https://arxiv.org/abs/1608.01948">B0950+08</a> is a nearby pulsar with a small DM. In this observation it is not very strong, but after folding the pulse is still visible. This is a good example of why we stack many pulses together.</p>
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
