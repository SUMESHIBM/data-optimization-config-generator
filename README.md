# Data Optimization Configuration Generator

A UX solution for IBM Instana's data usage optimization workflow, designed to help DevOps engineers quickly identify and implement optimization configurations for their services.
-------------------------------------------------------------------------------

## 🎯 Overview

**Problem Statement**

1.	**Complex Navigation**: 
Users must navigate through extensive tree-structured documentation to find relevant optimization information for their specific technology stack
2.	**Disconnected Experience**: 
The journey from identifying optimization opportunities (transparency view) to implementing solutions is fragmented across multiple interfaces and documentation pages
3.	**Support Dependency**: 
Many optimization requests are handled through support tickets due to the complexity of the current self-service experience


**Impact**
1.	High support ticket volume for optimization guidance
2.	User confusion and misinterpretation of documentation
3.	Delayed optimization implementation
4.	Poor user experience leading to underutilization of optimization features
5.	Out of scope: Time-consuming manual configuration across multiple agents

-------------------------------------------------------------------------------


**Scope of Work**

Phase 1: Contextual Optimization Discovery (Primary Focus)

1.1 Smart Jump-Out from Transparency View

Description:
Create contextual links from the usage transparency view that automatically identify the user's technology stack and direct them to relevant optimization options.

Requirements:
- Detect service technology stack (Java, JDBC, OpenTelemetry, Node.js, etc.)
- Display technology-specific optimization shortcuts directly in the transparency view
- Pre-filter optimization options based on detected technology
- Provide direct links to configuration generator with pre-selected technology

User Story:
> "As a DevOps engineer viewing my top data contributors, I want to see optimization options specific to my service's technology stack, so that I can quickly identify relevant optimizations without navigating documentation."



1.2 Configuration Generator Enhancement

Description:
Enhance the existing JDBC configuration generator to support multiple technologies and provide a more intuitive interface.

Requirements:
- Extend configuration generator beyond JDBC to support other technologies
- Accept URL parameters to pre-select technology and filters
- Provide drag-and-drop or preset-based configuration building
- Generate ready-to-use YAML files
- Display "what you see is what you get" preview of configuration
- Eliminate need to read extensive documentation

User Story:
> "As a DevOps engineer, I want to generate a YAML configuration file through an intuitive interface with presets, so that I don't have to manually read documentation and write configurations."



1.3 Optimization Catalog Integration

Description:
Create an in-product optimization catalog that replaces the current GitHub-based documentation tree.

Requirements:
- Centralized, searchable optimization catalog within the product
- Technology-based filtering and categorization
- Clear indication of which optimizations are available vs. in development
- Direct links from transparency view to relevant catalog entries
- Reduced reliance on external documentation

User Story:
> "As a DevOps engineer, I want to browse available optimizations within the product interface, so that I can quickly find and understand what's available for my technology stack."


Acceptance Criteria

Phase 1: Contextual Optimization Discovery

AC1: Technology-Specific Jump-Out
- [ ] When viewing a service in the transparency/usage view, the system detects the service's technology stack
- [ ] A contextual "Optimize" or similar action is displayed for services with available optimizations
- [ ] Clicking the action navigates to the configuration generator with technology pre-selected
- [ ] The configuration generator displays only relevant optimization options for the detected technology
- [ ] Users can access the optimization catalog without leaving the product interface

AC2: Enhanced Configuration Generator
- [ ] Configuration generator supports at least 3 technology types (starting with JDBC, expandable)
- [ ] Users can select from preset optimization configurations
- [ ] Users can customize configurations through an intuitive interface (drag-and-drop or form-based)
- [ ] Generated YAML file is syntactically correct and ready to use
- [ ] Users can preview the YAML before downloading/applying
- [ ] Configuration generator accepts URL parameters for pre-selection (technology, filters)

AC3: In-Product Optimization Catalog
- [ ] Optimization catalog is accessible from the transparency view
- [ ] Catalog can be filtered by technology type
- [ ] Each optimization entry clearly indicates availability status (available, in development, planned)
- [ ] Optimization descriptions are clear and include expected impact
- [ ] Users can navigate from catalog entry to configuration generator
- [ ] Catalog reduces need to access external GitHub documentation by 80%

AC4: User Journey Improvement
- [ ] Time from identifying optimization opportunity to generating configuration is reduced by 70%
- [ ] Users can complete optimization configuration without reading external documentation
- [ ] Support ticket volume for optimization guidance decreases by 50%
- [ ] User testing shows 90% task completion rate for generating optimization configurations

-------------------------------------------------------------------------------


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
