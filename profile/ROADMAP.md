# Development Roadmap

> **22-Day Action Plan** - Structured development phases with measurable KPIs

## Phase 1: Scope & Procurement (Day 1-2) ✅
**Focus**: Finalize MVP scope and purchase components

**Deliverables**:
- [x] Lock MVP scope definition
- [x] Create GitHub repository
- [x] Complete Bill of Materials (BOM)
- [x] Order all components
- [x] Document component arrival

**KPI**: ✅ 100% items ordered. Brainstorming session completed.

---

## Phase 2: Learning & Simulation (Day 3-4) ✅
**Focus**: Wokwi simulation and basic sensor testing

**Deliverables**:
- [x] Wokwi simulation: DHT22 + MQ-135 reading
- [x] Send dummy data to local endpoint
- [x] Validate sensor reading logic

**KPI**: ✅ Loop frequency ≥ 0.5 Hz, stable for 30 minutes. 0% data loss.

---

## Phase 3: Arduino Testing with Serial (Day 5-6) ✅
**Focus**: Hardware validation using Arduino Mega 2560

**Deliverables**:
- [x] Test sensors with Arduino Mega 2560
- [x] Send data via serial to laptop
- [x] Parse and save as JSON
- [x] Validate without ESP32-C3

**KPI**: ✅ Valid packets ≥ 95%. No hangs or crashes.

---

## Phase 4: ESP32-C3 Bring-up & Initial Wiring (Day 7-8) ✅
**Focus**: ESP32-C3 setup with WiFi and sensors

**Deliverables**:
- [x] Flash "Hello World" to ESP32-C3
- [x] WiFi connectivity established
- [x] Mount DHT22 & MQ-135 on breadboard
- [x] HTTP POST to local backend

**KPI**: ✅ P95 publish→ingest latency ≤ 400ms. Delivery rate ≥ 95% for 2 hours.

---

## Phase 5: Ngrok Integration + Backend & Database (Day 9-10) ✅
**Focus**: Public URL via Ngrok, backend API, MongoDB integration

**Deliverables**:
- [x] Activate Ngrok tunnel (`ngrok http 3000`)
- [x] Set `BACKEND_BASE_URL` in firmware/UI config
- [x] Implement `/ingest` endpoint
- [x] MongoDB data persistence
- [x] Health check endpoint (`/health`)

**KPI**: ✅ HTTP 200 via Ngrok. Write P95 latency ≤ 70ms. Zero 5xx errors.

---

## Phase 6: Real-time WebSocket/SSE via Ngrok (Day 11-12) ✅
**Focus**: Real-time data streaming through Ngrok domain

**Deliverables**:
- [x] WebSocket/SSE broadcast implementation
- [x] Configure CORS for `https://*.ngrok.io` origin
- [x] Real-time data push to clients

**KPI**: ✅ P95 end-to-end latency ≤ 250ms. 0% loss on 10k test messages.

---

## Phase 7: Minimal UI via Ngrok (Day 13-14) ✅
**Focus**: React dashboard with essential visualizations

**Deliverables**:
- [x] React-based web dashboard
- [x] Real-time gauge displays
- [x] Basic metrics panel
- [x] 24-hour historical graph (data from `/history` endpoint)
- [x] Environment variable configuration for Ngrok URL

**KPI**: ✅ API TTFB ≤ 250ms. UI load time ≤ 2 seconds.

---

## Phase 8: E2E Testing & URL Rotation (Day 15-16) ✅
**Focus**: Stability testing and Ngrok URL management

**Deliverables**:
- [x] WiFi disconnect/reconnect testing
- [x] Ngrok restart testing
- [x] `refresh-ngrok-url` script for environment updates
- [x] Automated URL propagation

**KPI**: ✅ Data completeness ≥ 99% over 2 hours. Downtime per rotation < 30 seconds.

---

## Phase 9: Calibration & Thresholds (Day 17-18) ✅
**Focus**: Sensor calibration and alert thresholds

**Deliverables**:
- [x] ADC to odor score mapping
- [x] Initial alert threshold configuration
- [x] Document test scenarios
- [x] Calibration procedure documentation

**KPI**: ✅ Drift < ±5 points over 15 minutes. False positive alerts ≤ 20%.

---

## Phase 10: Hardening & Logging (Day 19-20) ✅
**Focus**: Production readiness and monitoring

**Deliverables**:
- [x] Configure `ngrok.yml` (HTTP 3000, TCP 1883 optional)
- [x] Implement structured logging
- [x] Update README documentation
- [x] Error handling improvements
- [x] Connection resilience testing

**KPI**: ✅ Tunnel uptime ≥ 95% over 4 hours. Zero crashes.

---

## Phase 11: MVP Release via Ngrok (Day 21-22) 🔄
**Focus**: Final release and documentation

**Deliverables**:
- [x] Complete end-to-end demo
- [x] Record demo video
- [] Create release tag `mvp-v1`
- [x] Final documentation review
- [x] Regression testing

**KPI**:  All targets achieved. Regression tests passing.

---

## Overall MVP Success Criteria

| Metric | Target | Status |
|--------|--------|--------|
| **End-to-end data flow** | Sensors → Backend → Dashboard | ✅ Complete |
| **Stable operation** | 4+ hours continuous uptime | ✅ Achieved |
| **Data completeness** | ≥ 99% over 2 hours | ✅ Achieved |
| **API response time (P95)** | ≤ 250ms | ✅ Achieved |
| **UI load time** | ≤ 2 seconds | ✅ Achieved |
| **Alert accuracy** | False positives ≤ 20% | ✅ Achieved |
| **Documentation** | Complete setup & API docs | ✅ Partial |
| **Release tag** | `mvp-v1` published | ⏳ Pending |

---

## Post-MVP: Phase 12+ (Future Enhancements)

**Infrastructure Improvements**:
- [x] Migrate from Ngrok to permanent hosting (VPS/Cloud)
- [x] Domain with SSL certificate
- [x] Dedicated MQTT broker
- [ ] Database backup & recovery
- [x] Load balancing & scaling

**Feature Additions**:
- [x] User authentication & authorization
- [ ] Multi-room monitoring support
- [ ] Email/SMS alert notifications
- [ ] Mobile app (Android/iOS)
- [x] Advanced analytics dashboard
- [ ] Machine learning for odor prediction
- [ ] Sensor calibration UI
- [ ] OTA firmware updates
- [ ] Battery backup support
- [ ] Historical data export (CSV/Excel)

**Advanced Features**:
- [ ] Predictive maintenance alerts
- [ ] Integration with smart home systems
- [ ] API rate limiting & authentication
- [x] Grafana dashboard integration
- [ ] Custom alert rules engine
- [ ] Multi-sensor fusion algorithms
