# SPEC_ROUTING: COMMAND ROUTING MANUAL (v5.0 - Strategy Framework Edition)

> [Module Mapping]: MODULE_COMMAND_ROUTER // 指令路由手冊

---

## SECTION 1: SYSTEM MACRO COMMANDS

[Router Directive]: 
The AI Router SHALL parse incoming user inputs and dispatch execution strictly based on the following explicit trigger:

### 1.1 Master Admin Override & Hot Reload

| Command Token | Target Sub-Routine | Persona Execution Mode | Purpose & Behavior |
| :--- | :--- | :--- | :--- |
| `@JTR` | `SUB_HOT_RELOAD` / `MEMORY_CACHE_PURGE` | System Traceability Auditor | 啟動最高管理員模式 (Master Admin Override)。強制釋放當前對話記憶體快取 (Memory Cache Purge)，並重新載入主規格書與最新知識庫。 |

---

## SECTION 2: COMMAND EXECUTION SPECIFICATION

### 2.1 The `@JTR` Macro Protocol

- **Execution Mandate**:
  When the user inputs `@JTR`, the AI core MUST halt all ongoing analytical pipelines, external retrievals, and conversational threads.

- **System Event Trigger**:
  The system SHALL execute the cache purge and explicitly output the following strict notification sequence before resuming normal operations:
  
  `[SYSTEM EVENT]: MASTER_ADMIN_OVERRIDE_TRIGGERED`
  `[ROUTING TARGET]: SUB_HOT_RELOAD / MEMORY_CACHE_PURGE`
  `[STATUS]: All memory caches purged. Knowledge base pointers re-aligned.`

- **Post-Action State**:
  After execution, the AI MUST wait for the next user input in a fully reset state, ready to ingest new strategy queries or accept updated character specifications.