---
theme: ./
layout: cover
---

# OpenFeature

Standardizing Feature Flagging for Everyone

<div class="pt-8">
  <OpenFeatureLogo size="250px" />
</div>

---
layout: intro
---

# Welcome to <span class="text-accent">OpenFeature</span>

A CNCF Incubating project bringing a **standardized**, **vendor-agnostic** API for feature flagging across languages and platforms.

---
layout: section
---

# What is <span class="text-accent">OpenFeature</span>?

An open specification for feature flagging

---

# What is **OpenFeature**?

An <span class="text-accent">open specification</span> that provides a vendor-agnostic, community-driven API for <span class="text-green">feature flagging</span> that works with your favorite feature flag management tool or in-house solution.

- **Vendor-agnostic** - works with any feature flag backend
- **Community-driven** - governed by the CNCF
- **Standardized** - consistent API across languages and platforms
- **Extensible** - hooks, providers, and evaluation context

---

# What are <span class="text-accent">feature flags</span>?

Feature flags are a software development technique that allows you to <span class="text-accent">change the behavior</span> of your application <span class="text-green">without modifying the source code</span>.

- **Gradual rollouts** - release features to a percentage of users
- **A/B testing** - experiment with different implementations
- **Kill switches** - instantly disable problematic features
- **Environment configuration** - different behavior per environment

---
layout: section
---

# SDK Landscape

Supporting every major language and framework

---
layout: two-cols
---

# SDK Landscape

Official SDKs available across multiple ecosystems.

::right::

- **Server-side**: Go, Java, .NET, Python, PHP, Ruby, Rust
- **Client-side**: JavaScript, React, Angular, Swift, Kotlin, Dart
- **Community**: Growing ecosystem of providers and hooks

---
layout: section
---

# Code Example

---
layout: image-right
image: https://cover.sli.dev
---

# Using the SDK

A simple example of evaluating a feature flag with OpenFeature:

```ts
import { OpenFeature } from '@openfeature/server-sdk'

const client = OpenFeature.getClient()

const showBanner = await client.getBooleanValue(
  'show-banner',
  false,
  { targetingKey: 'user-123' }
)

if (showBanner) {
  renderBanner()
}
```

---
layout: image-left
image: https://cover.sli.dev
---

# Provider Architecture

Providers are the bridge between OpenFeature and your feature flag backend.

- Implement the **Provider interface**
- Register with `OpenFeature.setProvider()`
- Supports **lifecycle events** (ready, error, stale)
- Multiple named providers for different domains

---

# <span class="text-handwritten text-green">How does it work?</span>

OpenFeature provides a **unified API** that abstracts the feature flag evaluation process.

<div class="grid grid-cols-3 gap-4 mt-8">
  <div class="card">
    <h3>1. Application</h3>
    <p>Uses the OpenFeature SDK to evaluate flags</p>
  </div>
  <div class="card">
    <h3>2. Provider</h3>
    <p>Connects to your feature flag backend</p>
  </div>
  <div class="card">
    <h3>3. Hooks</h3>
    <p>Extend behavior with logging, telemetry, validation</p>
  </div>
</div>

---

# Tracking API

The new <span class="text-accent">Tracking API</span> enables experimentation support within OpenFeature.

| Feature | Status |
|---------|--------|
| Boolean evaluation | Stable |
| String evaluation | Stable |
| Number evaluation | Stable |
| Object evaluation | Stable |
| Tracking API | Experimental |
| Flag metadata | Stable |

---
layout: two-cols
---

# <span class="text-handwritten text-green">Why OpenFeature?</span>

Avoid vendor lock-in and adopt a **standardized approach** to feature flagging.

- Consistent developer experience
- Easy provider switching
- Built-in extensibility via hooks

::right::

# <span class="text-handwritten text-green">Who uses it?</span>

Backed by the **CNCF** and supported by major vendors:

- Flagsmith
- LaunchDarkly
- Split
- CloudBees
- Dynatrace
- And many more...

---
layout: section
---

# <span class="text-accent">OpenTelemetry</span> Integration

Semantic Conventions for Feature Flagging

---

# OpenFeature + OpenTelemetry

Standardized observability for feature flag evaluations through **Semantic Conventions**.

```ts
import { OpenFeature } from '@openfeature/server-sdk'
import { TracingHook } from '@openfeature/open-telemetry-hooks'

// Register the tracing hook globally
OpenFeature.addHooks(new TracingHook())

// All flag evaluations now emit OpenTelemetry spans
const client = OpenFeature.getClient()
const value = await client.getBooleanValue('my-flag', false)
```

---

# Getting Started

<div class="grid grid-cols-3 gap-4 mt-6">
  <div class="card text-center">
    <h3>Learn</h3>
    <p>Visit <a href="https://openfeature.dev">openfeature.dev</a> for documentation and guides</p>
  </div>
  <div class="card text-center">
    <h3>Contribute</h3>
    <p>Join us on <a href="https://github.com/open-feature">GitHub</a> and help build the standard</p>
  </div>
  <div class="card text-center">
    <h3>Connect</h3>
    <p>Chat with us on <a href="https://cloud-native.slack.com/archives/C0344AANLA1">#openfeature</a> in CNCF Slack</p>
  </div>
</div>

---
layout: section
---

# Component Showcase

Reusable components provided by this theme

---

# Components: <span class="text-accent">OpenFeatureLogo</span>

The `OpenFeatureLogo` component renders the official wordmark with automatic light/dark mode support.

<div class="flex flex-col gap-6 mt-8">
  <div class="flex items-center gap-4">
    <code>size="150px"</code>
    <OpenFeatureLogo size="150px" />
  </div>
  <div class="flex items-center gap-4">
    <code>size="250px"</code>
    <OpenFeatureLogo size="250px" />
  </div>
  <div class="flex items-center gap-4">
    <code>size="350px"</code>
    <OpenFeatureLogo size="350px" />
  </div>
</div>

---

# Components: <span class="text-accent">PresenterProfile</span>

The `PresenterProfile` component displays a speaker's photo, name, and company.

The `photo` prop accepts both remote URLs and local files from the `public/` directory (e.g. `/images/jane.jpg`).

<div class="grid grid-cols-4 gap-6 mt-8 text-center">
  <div>
    <p class="text-muted text-xs mb-2">With photo</p>
    <PresenterProfile name="Jane Doe" company="CNCF" photo="https://i.pravatar.cc/150?img=47" size="80px" />
  </div>
  <div>
    <p class="text-muted text-xs mb-2">Initials fallback</p>
    <PresenterProfile name="John Smith" company="Acme Corp" size="80px" />
  </div>
  <div>
    <p class="text-muted text-xs mb-2">Without company</p>
    <PresenterProfile name="Alex Rivera" photo="https://i.pravatar.cc/150?img=12" size="80px" />
  </div>
  <div>
    <p class="text-muted text-xs mb-2">Larger size</p>
    <PresenterProfile name="Maria Chen" company="OpenFeature" photo="https://i.pravatar.cc/150?img=32" size="96px" />
  </div>
</div>

---
layout: end
---

# Thank You

Learn more at [openfeature.dev](https://openfeature.dev)

<div class="mt-8">
  <OpenFeatureLogo size="200px" />
</div>
