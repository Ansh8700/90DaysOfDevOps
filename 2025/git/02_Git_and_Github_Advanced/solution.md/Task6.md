# ✅ Task 6: Branching Strategies in Companies

## 🔍 Common Git Workflows:

#### 1. **Git Flow**

* Branch Types: `main`, `develop`, `feature/*`, `release/*`, `hotfix/*`
* Suitable for: Large teams, multiple releases

#### 2. **GitHub Flow**

* Branch Types: `main`, `feature/*`
* PR-centric development
* Continuous delivery focused

#### 3. **Trunk-Based Development**

* All developers work on `main`
* Feature toggles used to manage unready code
* Emphasizes CI/CD, fast iterations

### 🧪 Simulated Workflow:

```bash
git branch feature-1
git branch hotfix-1
git checkout feature-1
```

### 💬 Which Is Best for DevOps/CI-CD?

**Trunk-Based Development** is most aligned:

* Encourages continuous integration
* Faster feedback cycles
* Fewer merge conflicts

### ⚖️ Pros and Cons:

| Workflow    | Pros                             | Cons                              |
| ----------- | -------------------------------- | --------------------------------- |
| Git Flow    | Structured, clear release cycles | Complex for small teams           |
| GitHub Flow | Simple, PR-driven                | Less structure for large releases |
| Trunk-Based | Fast, CI/CD optimized            | Needs discipline, feature flags   |

