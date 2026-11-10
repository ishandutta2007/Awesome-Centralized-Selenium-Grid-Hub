# Awesome-Centralized-Selenium-Grid-Hub

# Top Centralized Selenium Grid Hub Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Remote Browser Orchestration, Parallel Test Execution & Grid Infrastructure Management*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Centralized Selenium Grid Hub**. These tools provide a single endpoint for routing WebDriver sessions to remote browsers—enabling parallel test execution, cross-browser coverage, and centralized management of browser infrastructure without maintaining physical device labs or local grid nodes.

**Examples** include BrowserStack Hub, Selenium Grid Hub, Moon by Aerokube, Selenoid (archived), Zalenium (archived), Gridlastic, Sauce Labs Hub, LambdaTest Grid Hub, TestingBot Hub, and OpenSTF (legacy) (the category leaders).

**Open-source emphasis**: This section highlights every major active project for self-hosted Selenium grid hubs, containerized browser orchestration, and Kubernetes-native grid alternatives—ideal for QA engineers, platform teams, and organizations seeking transparent, vendor-neutral test infrastructure without per-session cloud pricing.

Contributions welcome! Open an PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-products)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[BrowserStack Hub](https://www.browserstack.com/)**  
  Cloud Selenium grid with access to 3,000+ real browsers and devices; point existing WebDriver tests at the BrowserStack hub endpoint with access credentials, no infrastructure to manage. Supports parallel test execution, local testing tunnels, and video/screenshot capture.

- **[Sauce Labs Hub](https://saucelabs.com/)**  
  Enterprise-grade Selenium cloud supporting Selenium, Playwright (via CDP), Cypress, and mobile testing. Playwright connections use Chrome DevTools Protocol over the Selenium Grid endpoint, with limitations including Chrome/Edge-only support and headed-mode requirement for video capture [citation:6]. Data centers in US and EU with compliance certifications.

- **[LambdaTest Grid Hub](https://www.lambdatest.com/)**  
  Selenium automation grid with 3,000+ browser and OS combinations; Jenkins plugin available for CI integration, including freestyle and pipeline job support, LambdaTest Tunnel for locally hosted applications, and test result viewing within Jenkins [citation:7].

- **[TestingBot Hub](https://testingbot.com/)**  
  Selenium cloud with 6,100+ real desktop browsers and physical iOS/Android devices. Change the WebDriver endpoint to `https://hub.testingbot.com/wd/hub` and pass credentials via `tb:options`; supports parallel execution, live video streaming, screenshots, and browser logs [citation:8].

- **[Gridlastic](https://www.gridlastic.com/)**  
  Auto-scaling Selenium grid on AWS with spot instance support for cost reduction. Grid hub runs 24/7; nodes auto-launch based on demand and terminate according to a configurable schedule. Gridlastic Connect provides encrypted tunnels for testing behind firewalls, and a pre-launch nodes API reduces startup latency [citation:15].

- **[Moon by Aerokube (Cloud)](https://aerokube.com/moon/)**  
  Kubernetes-native browser automation solution supporting Selenium, Playwright, Puppeteer, and Cypress in a single cluster. Pricing at $5 per parallel session per month; free tier supports up to 3 concurrent users with basic browser pools [citation:3][citation:12]. Enterprise adds RBAC, audit logging, SSO, priority queues, and multi-cluster scheduling.

- **[OpenSTF Hub (Legacy)](https://openstf.io/)**  
  Smartphone Test Farm for physical Android device labs with browser-based remote control, screen mirroring, shell access, app install, and REST API. The original repository went quiet around 2020; community continuation exists as DeviceFarmer/stf, but the stack carries legacy dependencies (RethinkDB, per-ABI native binaries) that complicate modern deployments [citation:9]. Best evaluated only if you already run STF and need a migration path.

- **[Zalenium (Archived)](https://opensource.zalando.com/zalenium/)**  
  Docker-based Selenium Grid with video recording, live preview, and dashboard. Built by Zalando to eliminate in-house grid maintenance; archived and no longer actively maintained. LambdaTest integration documentation still exists for teams extending Zalenium to cloud browsers [citation:4].

## Open-Source GitHub Projects

- **[Selenium Grid 4 (SeleniumHQ)](https://github.com/SeleniumHQ/selenium)**  
  The reference open-source implementation of the hub-and-node architecture. Grid 4 supports distributed execution with a hub (router, distributor, session map) and nodes registering browser capabilities; relay feature enables proxying Appium requests to Appium server instances [citation:1]. Actively maintained, Apache 2.0 licensed, and the foundation for most commercial and open-source alternatives.

- **[Moon by Aerokube (Self-Hosted)](https://github.com/aerokube/moon)**  
  Kubernetes-native browser automation platform supporting Selenium, Playwright, Puppeteer, and Cypress. Deploys via Helm with official Chrome, Firefox, and Edge images. Benchmarks show ~3s startup per session (K8s pod scheduling), ~250MB memory per browser, and 30+ max sessions on a 4-core host when cluster-scaled [citation:3]. Free tier available; paid adds RBAC, audit logging, SSO, and priority queues.

- **[WebSummoner (Selenoid Successor)](https://github.com/WebSummoner/websummoner)**  
  Go-based Selenium hub that launches browsers in ephemeral Docker containers per session; positioned as a maintained successor to Selenoid (archived December 2024). Apache 2.0 licensed, ~10MB binary with no Java dependency. Features video recording, live browser screen/logs, centralized logging, and backward compatibility with Selenoid client APIs including `selenoid:options` capability prefix and `/aerokube/...` proxy paths [citation:10].

- **[Selenoid (Archived)](https://github.com/aerokube/selenoid)**  
  Go-based Selenium hub using Docker containers for browsers; the project that popularized the "browser-in-container-per-session" model. Archived December 17, 2024, and no longer maintained [citation:13]. Benchmarks from its active period show ~2s session startup, ~300MB per browser, and 15–20 parallel sessions on a 4-core/16GB host [citation:3]. Existing deployments should evaluate WebSummoner or Moon as migration targets.

### Additional Strong Open-Source Options

- **[Selenium Grid on Railway (Template)](https://railway.com/deploy/selenium-grid-446-or-hub-chromium-and-fi)** — Deployable Grid 4 template with hub + Chromium/Firefox nodes, router basic auth, and pinned browser versions (Chromium 150, Firefox 152) for reproducible test runs [citation:11].
- **Community Selenium Grid Docker Compose stacks** — Many organizations maintain custom compose files for Grid 4 with browser-specific nodes and monitoring sidecars.
- **[Appium Grid Relay](https://appium.io/docs/en/3.1/guides/grid/)** — Official Appium guide for connecting Appium servers to Selenium Grid 4 via relay configuration, enabling mobile browser and native app testing through the same hub [citation:1].

**Frameworks for building custom systems**: Combine **Selenium Grid 4** for standards-compliant WebDriver routing, **WebSummoner** for Docker-native ephemeral browser sessions, and **Moon** for Kubernetes-scaled Playwright/Cypress execution—or deploy the **Railway template** for a pre-configured Grid 4 hub with authentication.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Selenium grid hubs, whether self-hosted or cloud, execute arbitrary browser automation commands; ensure proper authentication (basic auth at minimum), network isolation, and session cleanup to prevent resource exhaustion or unauthorized use.
- Self-hosted grid solutions require capacity planning, browser image updates, and monitoring; archived projects (Selenoid, Zalenium, OpenSTF) should be evaluated for migration rather than new deployments.

---

**Made for QA engineers, test automation architects, platform teams, and developers building scalable browser test infrastructure.**  
Let's make Selenium grid management more open, efficient, and maintainable.
