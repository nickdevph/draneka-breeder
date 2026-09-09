
# Breeder v1.0 Web Architecture

Status: IMPLEMENTATION-READY PLAN  
Product authority: canonical holistic v1.0 exact artifact  
Initial app: separate web application in nickdevph/draneka-breeder

## 1. Technology

Use the existing ecosystem's proven shape:

- React 19;
- TypeScript;
- Vite 8;
- Node server/API layer;
- pg for the restricted server-side Journal connection;
- Playwright for browser E2E;
- Vercel only after separate deployment admission.

The repository currently has no production source implementation, so this plan does not imply an existing app framework or authorize source creation before the first executable commission.

## 2. Canonical information architecture

Primary navigation remains exactly:

~~~text
Today | Programs | Log | Grow-out | More
~~~

Routes:

~~~text
/today
/programs
/programs/:programId
/log
/grow-out
/more
~~~

The foundation slice only needs Today, Programs, Program detail and the Log entry path needed to record output/hatch/group actions. Grow-out and More remain reserved shells until their packages are admitted. No new permanent navigation destination is introduced.

## 3. Authenticated shell

The shell:

1. asks the Breeder server for session state;
2. renders a loading state while session resolution is pending;
3. redirects to the existing Core sign-in path when unauthenticated;
4. never stores a database credential in browser storage;
5. carries only server-issued session cookies or the existing approved Core session mechanism;
6. shows a recoverable error when Core or Breeder session verification is unavailable.

The Breeder server owns Core session verification. Browser fields cannot select an account or owner subject.

## 4. Foundation screens

### Today

- current attention summary;
- Programs entry;
- no fabricated lifecycle facts;
- empty state explains how to create the first Program.

### Programs

- owner-scoped Program list;
- text search;
- deterministic no-results recovery;
- Active/Paused/Archived filters;
- create Program action;
- loading, retry and service-unavailable states.

### Program detail

- Program identity and species context;
- parent/source context;
- reproductive outputs;
- explicit hatch/recruitment action;
- offspring groups;
- current Journal tank location;
- committed readback after each mutation;
- clear labels for recorded fact, observation and suggestion.

### Log

- one-action access from primary navigation;
- bounded foundation actions only;
- validation errors adjacent to the field;
- no silent biological assertion from completing a suggestion.

## 5. Responsive and accessibility contract

The required CSS widths are 320, 390, 768 and 1440. At every width:

- no horizontal overflow;
- no clipped primary action;
- forms remain usable without hover;
- modal/sheet close, Escape and focus restoration work;
- touch targets meet the existing product baseline;
- keyboard can reach every action in logical order;
- visible focus is preserved;
- headings and labels are semantic;
- loading and error states are announced appropriately;
- empty states include an actionable recovery path.

## 6. Data and state model

Use a typed API client with:

- request cancellation for stale reads;
- query cache invalidation after committed mutations;
- no optimistic quantity mutation for biological commands;
- server readback as the source of truth;
- explicit retry only for safe GETs or idempotent mutations;
- visible conflict recovery that refreshes the entity and asks the user to retry.

Form state is local until the command is committed. A failed command must not appear in the timeline or quantity projection.

## 7. Media and Journal integration

The foundation slice does not need media creation. Later media flows reuse Journal media IDs and Journal privacy/public-evidence authorization. Breeder never uploads a private binary directly into a public handoff.

## 8. E2E acceptance

The first vertical slice must demonstrate:

~~~text
authenticated shell
  -> Today
  -> Programs
  -> create Program
  -> record output
  -> record explicit hatch
  -> create offspring group
  -> link same-owner Journal tank
  -> refresh
  -> read exact committed state
~~~

The browser test must also prove an owner-scope denial using a second test account and verify the recovery path for service, validation and empty states.
