## Executive Summary

This document outlines the requirements for improving the user experience around data usage optimization in Instana. The current process requires users to navigate complex documentation trees, manually configure YAML files, and apply changes across multiple agents without centralized management. This initiative aims to create a streamlined, contextual experience that connects transparency views directly to actionable optimization configurations.

---------------------------------------------------------------------------

**Problem Statement**

1.	**Complex Navigation**: 
Users must navigate through extensive tree-structured documentation to find relevant optimization information for their specific technology stack
2.	**Disconnected Experience**: 
The journey from identifying optimization opportunities (transparency view) to implementing solutions is fragmented across multiple interfaces and documentation pages
3.	**Support Dependency**: 
Many optimization requests are handled through support tickets due to the complexity of the current self-service experience

OUT OF SCOPE
4.	 **Manual Configuration**: 
Users must manually create YAML configuration files by reading documentation, which often leads to misunderstandings
5.	**Decentralized Agent Management**: 
No central configuration management exists - users must SSH into each agent machine individually to apply configurations


**Impact**
1.	High support ticket volume for optimization guidance
2.	User confusion and misinterpretation of documentation
3.	Delayed optimization implementation
4.	Poor user experience leading to underutilization of optimization features
5.	Out of scope: Time-consuming manual configuration across multiple agents


---------------------------------------------------------------------------


User Personas & Pain Points

Persona 1: DevOps Engineer / Site Reliability Engineer

**Goals:**
a.	Optimize data usage to stay within Fair Use Policy limits
b.	Reduce monitoring costs without losing visibility
c.	Quickly implement recommended optimizations


**Pain Points:**
•	"I see top contributors in the usage view, but I don't know which optimization applies to my specific technology stack (Java, JDBC, OpenTelemetry, etc.)"
•	"I have to read through extensive documentation to find the right YAML configuration for my service"
•	"Sometimes I misunderstand the documentation and implement the wrong optimization"
•	"I have to wait for support tickets to get guidance on what optimizations are available"
•	OUT of scope: "I need to SSH into 20+ agent machines individually to apply the same configuration change"


**Current Workflow:**
1. View usage transparency dashboard
2. Identify top contributors
3. Navigate to documentation tree
4. Search for technology-specific optimization guides
5. Read and interpret documentation
6. Manually create YAML configuration
7. SSH into each agent machine
OUT of scope:
8. Apply configuration to each agent individually
9. Restart each agent
10. Verify changes (no clear verification process)




OUT of scope:
Persona 2: Platform Engineering Manager

**Goals:**
a.	Ensure team stays within Fair Use Policy thresholds
b.	Standardize optimization configurations across the organization
c.	Minimize operational overhead

**Pain Points:**
- "I can't centrally manage agent configurations across my fleet"
- "I don't have visibility into which optimizations are already applied"
- "Rolling out configuration changes requires significant manual effort"
- "I need to ensure consistency across all agents but have no central control"


---------------------------------------------------------------------------


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






OUT of scope:
Phase 2: Agent Fleet Management Integration (Dependency)

Note: Agent Fleet Management is being developed by the Agent team in 2026. This phase focuses on UX integration and cross-team collaboration.

2.1 Cross-Team UX Coordination

Description:
Collaborate with Agent Fleet Management UX team to ensure seamless experience from optimization discovery to deployment.

Requirements:
- Identify Agent Fleet Management UX team contact and PM (Heading)
- Understand Agent Fleet Management roadmap and current progress
- Design integration points between optimization configuration and fleet deployment
- Ensure consistent user experience across both features



2.2 Configuration Deployment Experience

Description:
Design the end-to-end experience for deploying optimization configurations to agent fleets.

Requirements:
- Seamless handoff from configuration generator to fleet management
- Ability to preview which agents will be affected
- Bulk deployment capabilities
- Configuration verification and rollback options
- Status tracking for configuration deployment

**User Story:**
"As a DevOps engineer, I want to deploy my optimization configuration to all relevant agents from a central interface, so that I don't have to SSH into each machine individually."

---

Acceptance Criteria

Phase 2: Agent Fleet Management Integration

#### AC5: Cross-Team Integration
- [ ] Integration points with Agent Fleet Management are documented
- [ ] UX designs are reviewed and approved by both teams
- [ ] User flow from optimization configuration to deployment is seamless
- [ ] No duplicate functionality between optimization and fleet management features

#### AC6: Configuration Deployment (Dependent on Agent Fleet Management)
- [ ] Users can deploy configurations to multiple agents from a central interface
- [ ] Users can preview which agents will receive the configuration
- [ ] Deployment status is visible in real-time
- [ ] Users receive confirmation of successful deployment
- [ ] Rollback capability exists for failed deployments

---------------------------------------------------------------------------




**User Needs**

### Functional Needs

1. **Technology Detection**: Automatic identification of service technology stack
2. **Contextual Guidance**: Technology-specific optimization recommendations
3. **Configuration Generation**: Automated YAML file creation with presets
OUT of scope:
4. **Centralized Management**: Single interface for managing agent configurations
5. **Bulk Operations**: Apply configurations to multiple agents simultaneously
6. **Verification**: Clear feedback on configuration application success/failure

### Non-Functional Needs

1. **Discoverability**: Easy to find optimization options without extensive navigation
2. **Clarity**: Clear, unambiguous guidance on what each optimization does
3. **Efficiency**: Reduce time from identification to implementation
4. **Reliability**: Ensure configurations are applied correctly
5. **Consistency**: Standardized experience across all technology stacks

### Information Needs

1. **Availability**: Clear indication of which optimizations are currently available
2. **Applicability**: Understanding which optimizations apply to specific services
3. **Impact**: Expected results from applying optimizations
4. **Prerequisites**: Requirements or dependencies for each optimization
5. **Status**: Current configuration state across agent fleet

---------------------------------------------------------------------------


**Success Metrics**

### Primary Metrics
- **Reduction in support tickets** related to optimization guidance: Target 50% decrease
- **Time to implement optimization**: Target 70% reduction from current baseline
- **Self-service adoption rate**: Target 80% of users complete optimization without support
- **Configuration accuracy**: Target 95% of generated configurations are correct on first attempt

### Secondary Metrics
- **User satisfaction score** for optimization experience: Target 4.5/5
- **Feature adoption rate**: Target 60% of users with Fair Use Policy alerts use optimization features
- **Documentation access reduction**: Target 80% reduction in external documentation visits
- **Agent configuration time**: Target 90% reduction in time to configure multiple agents (post-fleet management)

---------------------------------------------------------------------------

**Dependencies & Constraints**

### Dependencies
1. **Agent Fleet Management**: Phase 2 depends on Agent Fleet Management feature development (2026 roadmap)
2. **Technology Team Optimization Frameworks**: Individual sensor teams continue developing optimization frameworks
3. **Configuration Generator**: Existing JDBC configuration generator serves as foundation
4. **Fair Use Policy**: Optimization features support Fair Use Policy compliance

### Constraints
1. **Scope Limitation**: This initiative focuses on UX/experience layer, not underlying optimization logic
2. **Cross-Team Coordination**: Requires collaboration with Agent team, sensor teams, and support
3. **Backward Compatibility**: Must support existing agent configurations
4. **Technology Coverage**: Initial release may not cover all technology stacks


---------------------------------------------------------------------------

## Research & Validation

**Required Research Activities
**
1. **Customer Interview Analysis**
   - Review existing support tickets (coordinate with Mark from customer support team)
   - Analyze French client interview from January 2026
   - Review Slack channel history for optimization-related discussions
   - Identify common patterns in customer confusion and requests

2. **Usability Testing**
   - Test current documentation navigation with 5-8 users
   - Validate proposed configuration generator interface
   - Test technology detection accuracy
   - Validate contextual jump-out placement and discoverability

3. **Competitive Analysis**
   - Review how other APM tools handle optimization configuration
   - Identify best practices for configuration generators
   - Analyze patterns for contextual help and guidance

### Validation Checkpoints

- **Design Review**: Share designs with clients for feedback (iterative approach)
- **Prototype Testing**: Test configuration generator with real users before development
- **Beta Testing**: Limited release to select customers before general availability
- **Post-Launch Review**: Gather feedback after 30 days of general availability

---------------------------------------------------------------------------

## Reference Materials

### Documentation
- **Fair Use Policy Overview**: Community page with Q4 2024 webinar recording and deck
- **Current Optimization Documentation**: GitHub-based "Optimize Data Ingest" knowledge dump
- **Technology-Specific Guides**: Individual sensor team documentation (JDBC, etc.)

### Access Points
- **Demo Instance**: Fair Use Policy banner and public documentation links
- **Community Page**: Data Usage and Optimization webinar materials
- **Support Tickets**: Contact Mark for customer support ticket exports

### Key Stakeholders
- **PM Lead**: Akash Thampi
- **Engineering**: Hubert Hesse, Domenico (configuration generator)
- **Agent Fleet Management PM**: Heading (to be confirmed)
- **UX Team**: Sumesh Somarajan, Emily Zhou, Tvisha Sharma
- **Customer Support**: Mark

---------------------------------------------------------------------------



## Appendix

### Glossary
- **Fair Use Policy**: Instana's data usage policy with defined thresholds
- **Transparency View**: UI showing data usage and top contributors
- **Configuration Generator**: Tool for creating YAML configuration files
- **Agent Fleet Management**: Upcoming feature for centralized agent configuration
- **Sensor**: Instana component that collects specific types of telemetry data
- **YAML**: Configuration file format used by Instana agents

---

**Document Version:** 1.0  

<img width="451" height="684" alt="image" src="https://github.com/user-attachments/assets/f7081e3a-6776-4cc3-9df4-8372715162d3" />
