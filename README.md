# Data Optimization Configuration Generator

A UX solution for IBM Instana's data usage optimization workflow, designed to help DevOps engineers quickly identify and implement optimization configurations for their services.

## 🎯 Overview

This project provides an intuitive interface for:
- Viewing data usage across services
- Discovering technology-specific optimization opportunities
- Generating YAML configurations with presets and custom filters
- Applying optimizations to Instana agents

## 📁 Project Files

### 1. **instana-data-optimization-ux.html**
The main Account and Billing page that displays:
- Service data usage table
- Technology stack identification
- Direct links to optimization configurations

**Live Demo:** [View Account & Billing Page](https://sumeshibm.github.io/data-optimization-config-generator/instana-data-optimization-ux.html)

### 2. **configuration-generator.html**
The Configuration Generator interface that provides:
- Pre-filled service details from URL parameters
- Technology-specific optimization presets
- Custom filter builder
- Real-time YAML generation
- One-click apply to Instana

**Live Demo:** [View Configuration Generator](https://sumeshibm.github.io/data-optimization-config-generator/configuration-generator.html?service=qotd-web&technology=Node.js&framework=OpenTelemetry&usage=22)

### 3. **product-requirements-data-optimization-ux.md**
Complete Product Requirements Document including:
- User personas and pain points
- Scope of work
- Acceptance criteria
- Success metrics

## 🚀 Features

### Account & Billing Page
- ✅ Clean, IBM Carbon Design System UI
- ✅ Service usage table with percentages
- ✅ "View Optimizations" links per service
- ✅ Contextual navigation to Configuration Generator

### Configuration Generator
- ✅ Auto-populated service details
- ✅ Technology-specific optimization presets
- ✅ Custom filter builder with drag-and-drop
- ✅ Live YAML preview
- ✅ Copy/Download configuration
- ✅ Apply to Instana with one click

## 💡 User Flow

1. **Discover** → View services with high data usage in Account & Billing
2. **Select** → Click "View Optimizations" for any service
3. **Configure** → Choose presets or create custom filters
4. **Apply** → Copy YAML and apply to Instana agents

## 🎨 Design System

Built with **IBM Carbon Design System v11** components:
- Carbon color tokens
- IBM Plex Sans typography
- Standard spacing and layout patterns
- Accessible components with ARIA labels

## 📊 Success Metrics

- **50% reduction** in support tickets for optimization guidance
- **70% faster** time to implement optimizations
- **80% self-service** adoption rate
- **95% accuracy** in generated configurations

## 🔗 Links

- **Account & Billing:** [instana-data-optimization-ux.html](instana-data-optimization-ux.html)
- **Configuration Generator:** [configuration-generator.html](configuration-generator.html)
- **Product Requirements:** [product-requirements-data-optimization-ux.md](product-requirements-data-optimization-ux.md)

## 👥 Team

- **Product Managers:** Hubert Hesse, Akash Thampi
- **UX Design:** Sumesh Somarajan, Emily Zhou, Tvisha Sharma
- **Engineering:** Domenico (Configuration Generator)

## 📝 License

Internal IBM Project - 2026

---

**Note:** This is a design prototype. For production implementation, integrate with Instana's backend APIs for real-time data and agent management.
