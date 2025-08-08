# The Decision Approval System: A Protocol for Human-AI Collaboration

## The Problem: Agents Making Unilateral Architectural Decisions

When working with AI coding assistants, we've observed a critical failure pattern: **agents make instant, unilateral decisions about architecture, dependencies, and design patterns without recognizing these as collaborative decision points.**

### Examples of the Problem

```
Human: "Add user authentication to the app"

AI Agent: [Immediately installs passport, bcrypt, jsonwebtoken, express-session]
         [Creates /src/auth/strategies/]
         [Implements JWT + OAuth hybrid]
         [Adds three middleware layers]
         
Human: "Wait, we already use NextAuth..."
```

The agent made at least 10 architectural decisions without consultation:
- Authentication library selection
- Password hashing approach  
- Session management strategy
- Directory structure
- Middleware architecture
- Token format
- And more...

### Why This Happens

LLM agents are trained on millions of code examples where these decisions were already made. They pattern-match and implement the most common solution, not recognizing that **commonality doesn't equal correctness** for a specific project.

They treat architectural choices as implementation details, diving straight into code without considering:
- Existing patterns in the codebase
- Team preferences and standards
- Performance vs. complexity trade-offs
- Long-term maintenance implications
- Security and compliance requirements

## The Solution: A Decision Approval System

We propose a formal system where agents must recognize, categorize, and collaborate on decisions before implementing them.

### Core Concept

Just like command-line tools ask for permission before dangerous operations:
```bash
$ rm -rf node_modules/
> Are you sure? [y/N]
```

Agents should recognize decision points and seek appropriate approval:
```
Agent: "I need to add authentication. This is a Technical Architecture decision.

Options:
1. NextAuth.js - Full-featured, works with your Next.js app
2. Passport.js - Flexible but requires more setup
3. Custom JWT - Lightweight but more maintenance

Current project uses NextAuth for the admin panel.
I recommend extending that.

How should I proceed?"
```

### Decision Categories with Trust Levels

The system defines categories of decisions, each with configurable autonomy levels:

| Category | Examples | Default Policy |
|----------|----------|---------------|
| **Technical Architecture** | Database choice, API design | Present options |
| **Package Selection** | npm dependencies | Present options |
| **Code Organization** | File structure, module boundaries | Recommend & wait |
| **External Integrations** | APIs, services, telemetry | Require approval |
| **Security Decisions** | Auth, encryption, secrets | Require approval |
| **Testing Strategy** | Test types, mocking approach | Recommend & wait |
| **Naming Conventions** | Variable/function names | Decide & report |

### Progressive Trust Model

The system starts locked down and builds trust progressively:

```yaml
# Day 1: Everything requires approval
package_selection: require_approval

# Week 2: User sees good package choices
package_selection: present_options

# Month 2: Agent has proven good judgment
package_selection: auto_decide
```

Users can adjust policies in real-time:
- **"Always"** - Grant autonomy for this category
- **"Never"** - Always require approval
- **"This time"** - One-time decision, don't change policy

### How It Works in Practice

#### 1. Agent Detects Decision Point
```typescript
// Agent recognizes: "I need an HTTP client - this is package_selection"
```

#### 2. Agent Checks Policy
```yaml
# In policies.yaml
package_selection: 
  current_policy: "present_options"
```

#### 3. Agent Presents Options
```markdown
## Decision Required: Package Selection

**Context:** Need HTTP client for API calls
**Risk Level:** Medium

### Options:
1. **axios** - 61M weekly downloads, 5.5KB gzipped
   - Pros: Popular, interceptors, browser/node
   - Cons: Extra dependency, larger than fetch

2. **Built-in fetch** - Native Web API
   - Pros: No dependency, standard API
   - Cons: Needs wrapper for nice features

3. **ky** - 2M weekly downloads, 3KB gzipped
   - Pros: Tiny, modern, good DX
   - Cons: Less popular, newer

How should I proceed? [1/2/3/A/N]
```

#### 4. User Responds
```
User: "2A" (Use fetch and always auto-decide packages)
```

#### 5. Decision is Logged
```yaml
decision_log:
  - timestamp: "2024-08-08T20:30:00Z"
    category: "package_selection"
    decision: "Built-in fetch"
    policy_updated: true
    new_policy: "auto_decide"
```

## Key Benefits

### 1. **No More Surprise Architectures**
Users aren't ambushed by unexpected technical decisions buried in code.

### 2. **Progressive Autonomy**
As trust builds, interruptions decrease. Eventually, agents make routine decisions independently.

### 3. **Audit Trail**
Every architectural decision is logged with context, alternatives considered, and rationale.

### 4. **Team Alignment**
Decisions become visible and discussable, not hidden in implementation details.

### 5. **Learning from Decisions**
Patterns emerge that can be codified into project standards.

## Advanced Capabilities

### Recursive Delegation for Multi-Agent Systems

As AI systems grow to include specialized sub-agents, the same protocol works hierarchically:

```
User grants authority to → Lead Agent
                          ↓
                    Lead Agent delegates to → Research Agent
                                              ↓
                                        Research Agent asks → Implementation Agent
```

Each level has its own trust boundaries, creating traceable chains of authority.

### Decision Simulation Mode

Before starting work, agents can identify all decision points:
```
Agent: "This task will require decisions about:
        - Database schema design (technical_architecture)
        - 2-3 npm packages (package_selection)
        - Test approach (testing_strategy)
        
        Would you like to pre-approve any categories?"
```

### Cross-Project Learning

Policies can be shared across projects, capturing team or personal preferences:
- "This user always prefers minimal dependencies"
- "This team requires approval for database changes"
- "This organization mandates security reviews"

## Implementation Status

We've implemented this system in our project with:
- Formal decision categories and policies
- YAML-based configuration
- Decision logging with full context
- Integration into agent prompts
- Template for decision presentation

Initial results show:
- Agents now recognize decision points consistently
- Surprise architectural changes eliminated
- Clear audit trail of all decisions
- Users report feeling more in control

## Open Questions for Feedback

1. **Granularity**: Are these the right categories? Too many? Too few?

2. **Default Policies**: Should we start more locked down or more permissive?

3. **UI/UX**: How can we make decision presentation less intrusive while maintaining clarity?

4. **Team Dynamics**: How should this work with multiple humans and agents?

5. **Performance**: How do we balance decision quality with development speed?

## Conclusion

The Decision Approval System transforms AI agents from autonomous actors making hidden choices into collaborative partners who respect boundaries, build trust progressively, and maintain accountability.

It's not about limiting AI capabilities—it's about making architectural decisions explicit, collaborative, and traceable. The result is AI assistance that feels less like autopilot and more like pair programming with a respectful colleague who knows when to ask for input.

## Try It Yourself

The full implementation is available at: [github.com/your-repo]

Configuration examples:
- Conservative: `policies-conservative.yaml`
- Balanced: `policies-balanced.yaml`  
- Trusting: `policies-trusting.yaml`

We welcome feedback on the approach, implementation, and potential extensions.

---

*This system emerged from real frustration with AI agents making instant assumptions about architectural decisions. After watching agents repeatedly "dive in" with unilateral choices about packages, structure, and patterns, we designed this protocol to make decision points explicit and collaborative.*
