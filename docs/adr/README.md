# Architecture decisions

| ADR | Decision | Why, in one line |
|---|---|---|
| 0001 | Hard-block only sources that completed a TCP handshake | A packet's source address is a claim; a finished handshake is proof |
| 0002 | eBPF/XDP instead of an out-of-tree kernel module | The verifier rejects unsafe code before it runs, and XDP sees packets first |
| 0003 | Track state per flow, not counters per IP | Slow and distributed scans hide under per-IP counters |
| 0004 | Fast path in the kernel, slow path in Python, joined by BPF maps | Reflex in the kernel, judgment in Python |
| 0005 | Every block has an expiry and cites its evidence | Wrong blocks must be explainable and undoable |
