---
layout: page
title: Principles of Machine Learning at Network School
description: Landing page for Machine Learning classes available to Network School residents.
permalink: /machine-learning/
---

<section class="course-hero">
  <p class="course-eyebrow">Network School · Forest City, Malaysia</p>
  <h1>Principles of Machine Learning</h1>
  <p class="course-lead">A practical, intuition-first machine learning course for founders and builders who want to understand the modern AI stack without getting lost in jargon.</p>
  <p>We focus on the full pipeline behind today’s AI systems: data, pretraining, posttraining, inference, APIs, local models, and the mental models you need to reason about capability, cost, and scale.</p>
  <p class="course-cta-row">
    <a class="course-cta" href="#curriculum">See the curriculum</a>
    <a class="course-secondary" href="#hands-on">Hands-on projects</a>
  </p>
</section>

<hr class="break">

<section>
  <h2>What the course is for</h2>
  <p>This course is built for smart, motivated people who are technical enough to build companies and products, but who do not necessarily have a machine learning background. The goal is demystification: by the end, models should feel less like magic and more like systems you can inspect, run, and reason about.</p>

  <div class="course-grid-two">
    <div class="project">
      <h3>Clear mental models</h3>
      <p>Learn where data, training, posttraining, inference, APIs, and local models fit in the modern ML pipeline.</p>
    </div>
    <div class="project">
      <h3>Technical honesty, low formalism</h3>
      <p>We avoid unnecessary math, but keep the core ideas accurate enough to support real engineering decisions.</p>
    </div>
    <div class="project">
      <h3>LLM-heavy by design</h3>
      <p>The framing is machine learning, but the center of gravity is modern deep learning and the LLM pipeline.</p>
    </div>
    <div class="project">
      <h3>Built around builders</h3>
      <p>Examples emphasize product intuition, system tradeoffs, local inference, and what it takes to ship with models.</p>
    </div>
  </div>
</section>

<hr class="break">

<section id="curriculum">
  <h2>Core curriculum</h2>
  <ol class="course-steps">
    <li>
      <strong>Full pipeline overview.</strong>
      <p>Data → pretraining → posttraining → inference → model APIs, with a practical “where are you in the pipeline?” mental model.</p>
    </li>
    <li>
      <strong>Pretraining deep dive.</strong>
      <p>Neural network internals, tokenization, embeddings, gradient descent, the training loop, and live intuition-building demos.</p>
    </li>
    <li>
      <strong>Posttraining deep dive.</strong>
      <p>Base models vs. chat models, instruction tuning, RLHF, RAG, and the difference between capability and behavior.</p>
    </li>
    <li>
      <strong>Running local models.</strong>
      <p>Survey local options across modalities, compare model sizes, and get participants running models on their own machines.</p>
    </li>
  </ol>
</section>

<hr class="break">

<section>
  <h2>Ideas that come up again and again</h2>
  <p>These are the recurring themes that anchor the course as it evolves between cohorts.</p>

  <ul class="course-checklist">
    <li>Models are numbers in files; training adjusts those numbers to reduce error.</li>
    <li>Scale matters: pretraining, posttraining, local models, and frontier models differ by orders of magnitude.</li>
    <li>Embeddings are everywhere: tokens, retrieval, CLIP, and “meaning as position in vector space.”</li>
    <li>The training loop is universal: forward pass → loss → backward pass → update.</li>
    <li>Pretraining creates capability; posttraining shapes behavior.</li>
    <li>Deep learning wins on unstructured data, while tools like XGBoost remain strong for tabular problems.</li>
  </ul>
</section>

<hr class="break">

<section id="hands-on" class="course-final-cta">
  <h2>Hands-on track</h2>
  <p>The course is paired with project sessions where students run local models, experiment with practical tooling, and connect the concepts to real systems. The broader NS makerspace track also includes robotics work with LeRobot SO-ARM100 arms, custom 3D-printed parts, and hackathons around robotics and drones.</p>
  <p>This is a living curriculum. I revise the session order, demos, and emphasis between cohorts based on what actually helps students build intuition.</p>
</section>
