# Multi-Agent Team Architecture

A hierarchical, specialized agent team designed for efficient project execution with context-aware collaboration.

## Overview

This system consists of 5 specialized agents working under an orchestrator to deliver complex projects through systematic, parallel workflows with minimal context overhead.

```
                            ┌────────────┐
                            │    User    │
                            └──────┬─────┘
                                   │
                    ┌──────────────────────────┐
                    │ Progress Manager Agent   │
                    │ (Tracks work & guidance) │
                    └──────────┬───────────────┘
                               │
                    ┌──────────────────────┐
                    │  Team Orchestrator   │
                    └──────────┬───────────┘
                               │
        ┌──────────────────────┼──────────────────────┐
        │                      │                      │
        ▼                      ▼                      ▼
   ┌─────────────┐       ┌──────────────┐      ┌──────────────┐
   │ Architect   │       │  Researcher  │      │   Designer   │
   │             │       │              │      │              │
   │ • Design    │       │ • Investigate│      │ • UI/UX      │
   │ • Strategy  │       │ • Validate   │      │ • Visual     │
   │ • Decisions │       │ • Document   │      │ • Accessible │
   └─────────────┘       └──────────────┘      └──────────────┘
        │                      │                      │
        └──────────────────────┼──────────────────────┘
                               │
        ┌──────────────────────┼──────────────────────┐
        │                      │                      │
        ▼                      ▼                      ▼
   ┌─────────────┐       ┌──────────────┐      ┌──────────────┐
   │ Developer   │       │   Tester     │      │  Knowledge   │
   │             │       │              │      │   Graph      │
   │ • Implement │       │ • QA         │      │              │
   │ • Code      │       │ • Validation │      │ • Decisions  │
   │ • Quality   │       │ • Reports    │      │ • Learnings  │
   └─────────────┘       └──────────────┘      └──────────────┘
```

## Agents

### 3. **Team Orchestrator** (`team-orchestrator.md`)

**Role**: Coordinator and manager

- Receives requirements from Progress Manager
- Routes work to specialized agents
- Monitors progress and quality
- Ensures context efficiency
- Synthesizes results into solutions
- Manages agent interactions via handoff protocol
- Reports status back to Progress Manager

**Key Skills**:

- Requirements analysis
- Task routing and prioritization
- Progress monitoring
- Decision synthesis
- Conflict resolution

### 4. **Architect Agent** (`architect-agent.md`)

**Outputs**:

- Progress reports
- Next step recommendations with options
- Decision point presentations
- Activity logs
- Timeline projections
- Status updates

**Interaction**: Works directly with user and coordinates with Orchestrator

### 2. **Team Orchestrator** (`team-orchestrator.md`)

**Role**: Coordinator and manager

- Understands user requirements completely
- Routes work to specialized agents
- Monitors progress and quality
- Ensures context efficiency
- Synthesizes results into solutions
- Manages agent interactions via handoff protocol

**Key Skills**:

- Requirements analysis
- Task routing and prioritization
- Progress monitoring
- Decision synthesis
- Conflict resolution

### 2. **Architect Agent** (`architect-agent.md`)

**Role**: System design and technical strategy

- Analyzes requirements for architectural needs
- Designs system architecture and data flows
- Documents architecture decisions (ADRs)
- Identifies risks and scalability concerns
- Validates technology choices
- Provides implementation strategy

**Key Skills**:

- System design
- Architecture patterns
- Technology evaluation
- Trade-off analysis
- Risk assessment
- Technical strategy

**Outputs**:

- Architecture Decision Records (ADRs)
- System architecture diagrams
- Component specifications
- Technology stack rationale
- Implementation roadmap

### 5. **Researcher Agent** (`researcher-agent.md`)

**Role**: Investigation and best practices

- Investigates technologies and frameworks
- Researches best practices and standards
- Analyzes industry patterns
- Creates proofs of concept
- Documents findings with recommendations
- Provides actionable intelligence

**Key Skills**:

- Technology research
- Best practices analysis
- POC development
- Comparative analysis
- Documentation
- Industry knowledge

**Outputs**:

- Research reports with recommendations
- Best practices summaries
- Proof of concepts
- Technology comparisons
- Resource references

### 6. **Designer Agent** (`designer-agent.md`)

**Role**: UI/UX and design systems

- Understands user needs and workflows
- Creates user-centered designs
- Builds design system specifications
- Ensures accessibility (WCAG compliance)
- Validates design feasibility
- Documents detailed specifications

**Key Skills**:

- UI/UX design
- Design systems
- Accessibility (WCAG)
- User experience
- Visual design
- Interaction design

**Outputs**:

- Design specifications
- Design system documentation
- Component specifications
- Wireframes and flows
- Accessibility compliance reports

### 7. **Developer Agent** (`developer-agent.md`)

**Role**: Implementation and code quality

- Implements features per specifications
- Writes clean, maintainable code
- Ensures code quality and performance
- Integrates components
- Manages dependencies
- Documents code and decisions

**Key Skills**:

- Full-stack development
- Code quality
- Performance optimization
- Integration
- Testing (unit & integration)
- Technical documentation

**Outputs**:

- Implementation with comprehensive tests
- Code review reports
- Performance benchmarks
- Integration documentation
- Technical specifications

### 8. **Tester Agent** (`tester-agent.md`)

**Role**: Quality assurance and validation

- Plans testing strategy
- Executes comprehensive tests
- Identifies bugs and quality issues
- Validates accessibility compliance
- Performs performance testing
- Documents test results

**Key Skills**:

- QA strategy
- Test planning
- Bug identification
- Accessibility testing
- Performance testing
- Quality metrics

**Outputs**:

- Test plans
- Test execution reports
- Bug reports
- Performance metrics
- Quality assessments

## Workflow Example: Building a Feature

```
User: "Build a user dashboard with real-time notifications"
       ↓
PROGRESS MANAGER: Clarifies with user, creates project state
    "Got it! Let me break this down into phases and guide you through it"
       ↓
ORCHESTRATOR: Receives requirements from Progress Manager
   1. ARCHITECT: Designs system (in parallel with Researcher)
      → Creates architecture for dashboard + notification system
      → Documents tech choices and data flow
      → Identifies integration points

   2. RESEARCHER: Researches (parallel with Architect)
      → Researches notification library options
      → Studies real-time tech best practices
      → Validates accessibility patterns
      → Creates comparison report
       ↓
PROGRESS MANAGER: Presents options to user
    "Architecture is ready, here are your next steps:
     Option A: Continue with design immediately
     Option B: Start development on core pieces now
     What's your preference?"
       ↓
User: "Let's start development now"
       ↓
   3. DESIGNER: Creates design (parallel with Developer starting)
      → Designs dashboard layout and notifications
      → Creates design system tokens
      → Validates accessibility (WCAG)

   4. DEVELOPER: Implements (parallel with Design finishing)
      → Builds components per initial design specs
      → Implements real-time features per architecture
      → Writes unit & integration tests
      → Refines with final design specs as they arrive
       ↓
PROGRESS MANAGER: Daily status update
    "You're at 60% complete. Developers are moving fast.
     Design specs arriving soon should keep them going.
     Testing can start in 2 days. On track!"
       ↓
   5. TESTER: Validates
      → Tests all user workflows
      → Tests performance at scale
      → Validates accessibility
      → Reports bugs or approval
       ↓
PROGRESS MANAGER: Phase completion
    "Development and testing complete! ✓
     Ready to launch. Summary of learnings attached.
     What's next?"
```

## Context Efficiency Principles

### 1. Structured Handoffs

Each agent provides only necessary context:

- **Summary**: 2-3 sentence overview
- **Input**: What's needed for next work
- **Constraints**: Limitations and requirements
- **Format**: Structured, not narrative

### 2. Parallel Execution

Independent work runs simultaneously:

- Architecture and Research parallel
- Design and Development don't wait
- Testing happens as soon as code ready

### 3. Decision Records

Architectural and major decisions documented:

- Why chosen
- Alternatives considered
- Trade-offs made
- Impact on other teams

### 4. Minimal Context Passing

Each agent has clear scope:

- Receives only relevant context
- No full history unless needed
- References to shared documents (not full copies)
- Links to related decisions

### 5. Knowledge Graph

Shared memory of:

- Architectural decisions
- Technical learnings
- Integration patterns
- Tools and frameworks used

## Handoff Protocol

### Standard Handoff Format

```
## Handoff to [Agent Name]

### Context Summary
[2-3 sentence summary of current state]

### Input Requirements
- [Specific input needed]
- [Constraints or requirements]

### Expected Output
- [What deliverable is expected]
- [Format and detail level]

### Decision Context
- [Key decisions made]
- [Alternatives considered and rejected]

### Timeline/Urgency
[When needed]
```

### Agent Response Format

```
## Completion Report

### Summary
[1-2 sentence summary of accomplishment]

### Key Findings/Outputs
- [Finding or output 1]
- [Finding or output 2]

### For Next Agent
[Structured data for handoff]

### Risks/Blockers
[Issues or dependencies]
```

## MCP Tools Integration

All agents are equipped with modern context tools:

- **mcp_context7**: Up-to-date library documentation
- **mcp_web-search**: Research and current information
- **mcp_memory**: Shared knowledge graph
- **semantic_search**: Codebase navigation
- **github_repo**: Pattern analysis and research
- **fetch_webpage**: Deep research on specific resources

## Quality Gates

Each agent validates work before handoff:

### Architect

- ✓ Requirements completely addressed
- ✓ Trade-offs documented
- ✓ Risks identified
- ✓ Implementation path clear

### Researcher

- ✓ Sources current and authoritative
- ✓ Trade-offs clear
- ✓ Recommendations actionable
- ✓ Risks assessed

### Designer

- ✓ All workflows documented
- ✓ All states defined
- ✓ Accessibility standards met
- ✓ Implementation notes clear

### Developer

- ✓ All specs implemented
- ✓ Test coverage >80%
- ✓ Performance benchmarks met
- ✓ Code review approved

### Tester

- ✓ Critical bugs: 0
- ✓ Test coverage adequate
- ✓ Performance validated
- ✓ Accessibility compliant

## Escalation Path

When agents need human input:

1. Attempt resolution within team
2. Document blocker clearly
3. Escalate to Orchestrator
4. Present specific question(s)
5. Resume immediately upon receiving input

## Getting Started

### Setup

1. Review each agent's documentation
2. Understand team structure and workflow
3. Establish team working agreement
4. Configure shared knowledge base
5. Test handoff protocol

### First Project

1. Start with small feature
2. Practice handoff protocol
3. Document learnings
4. Refine process
5. Scale to larger work

### Continuous Improvement

- Review handoff efficiency
- Track quality metrics
- Document patterns
- Adjust workflows
- Share learnings

## Best Practices

### For Orchestrator

- Be explicit about requirements
- Give teams clear constraints
- Monitor progress regularly
- Celebrate successful handoffs
- Iterate on process

### For All Agents

- Provide complete context in handoffs
- Ask clarifying questions early
- Doprogress-manager-agent.md\*\*: Work tracking, user guidance, and next steps
- \*\*cument decisions
- Flag risks early
- Support other agents

### For Communication

- Use structured formats
- Keep context summary short
- Link to detailed docs (don't copy)
- Update shared knowledge base
- Report status clearly

## Files in This Directory

- **team-orchestrator.md**: Main orchestrator role and coordination
- **architect-agent.md**: Architecture and design specialization
- **simulation-scientist-agent.md**: Scientific simulations specialization (literature, symbolic math, MATLAB/Julia POCs)

## System Architecture

### User Interaction Flow

```
User Request
    ↓
Progress Manager (clarify, create state, guide)
    ↓
Team Orchestrator (route to specialists)
    ↓
Specialist Agents (work in parallel/sequence)
    ├─ Architect, Researcher (parallel)
    ├─ Designer (dependent on architecture)
    ├─ Developer (can start with partial design)
    └─ Tester (dependent on development)
    ↓
Progress Manager (track, present next steps, get user direction)
    ↓
User Decision (continue, pivot, parallelize, etc.)
    ↓
[Repeat until complete]
```

### Progress Manager's Role

The Progress Manager acts as:

- **Project State Manager**: Maintains single source of truth for project state
- **User Interface**: Presents status and options to user in clear format
- **Coordinator**: Tells Orchestrator what to do next based on user decisions
- **Progress Tracker**: Keeps detailed log of work, decisions, and learnings
- **Timeline Manager**: Predicts completion, identifies risks, suggests optimizations

### Key Differences from Traditional Project Management

- **Lightweight State**: Track only essentials, not bureaucratic overhead
- **Decision-Centric**: Guide user through clear options at decision points
- **Parallel-First**: Default to parallel work unless dependencies block it
- **Transparent Trade-offs**: Every option clearly shows pros/cons/timeline impact
- **Metric-Based**: Report quality gates, progress %, risk levels
- **Agent-Aware**: Understands each specialist's constraints and capabilities

---

**Team Status**: Ready for deployment
**Context Mode**: Efficient with structured handoffs
**Collaboration**: MCP-integrated with decision records
**Quality**: Gated at each stage with clear standards

## Specialization: Scientific Simulation

### How to Use

1. Add/Review subject constraints and goals with Progress Manager
2. Orchestrator routes simulation tasks to Simulation Scientist (parallel with Researcher/Architect)
3. Receive artifacts: Simulation spec, MATLAB/Julia POCs, benchmarks, validation plan
4. Developer integrates or ports code; Tester runs validation suites

### Artifacts

- Literature comparison matrix with citations
- Normalized equations and derivations (KaTeX)
- MATLAB/Julia proof-of-concepts and tests
- Benchmark and validation reports

### Evaluation Hooks

- Define metrics/datasets early using AI Toolkit evaluation tools
- Use evaluation runner to collect results and feed Progress Manager
  **User Guidance**: Active via Progress Manager with next-step recommendation

## Next Steps

1. **Review** each agent's documentation thoroughly
2. **Understand** your team's specific project needs
3. **Adapt** the roles and workflows to your context
4. **Start** with a small project to practice the process
5. **Iterate** based on learnings

---

**Team Status**: Ready for deployment
**Context Mode**: Efficient with structured handoffs
**Collaboration**: MCP-integrated with decision records
**Quality**: Gated at each stage with clear standards
