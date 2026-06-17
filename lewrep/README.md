 # lewrep2 🏎️💨 — Ultra‑Fast Parallel Text Search for Modern Systems

lewrep2 is a high‑performance, cross‑platform CLI search utility written in Rust. It recursively scans directories for patterns with minimal overhead, delivering near‑instant results even on large codebases.
Built on the same industrial‑strength foundations that power ripgrep — grep‑searcher, grep‑regex, and ignore — lewrep2 strips away initialization bloat and executes with a lean, aggressively optimized pipeline.
Designed for developers, sysadmins, and power users, lewrep2 integrates seamlessly into UNIX‑style workflows and supports full piping compatibility with tools like grep, ripgrep, tree, cat, ls, and more.

# 🚀 Why lewrep2 Exists

lewrep2 was engineered with a simple philosophy:
If a search tool exists, it should be as fast as the machine allows — no excuses, no wasted cycles.
Where many tools add layers of abstraction, lewrep2 focuses on:
• raw speed • predictable behaviour • parallel execution • zero‑copy data flow • minimal memory footprint.

# 📊 Benchmark: Micro‑Scan Performance (Apple Silicon)

Measured using high‑precision telemetry from lewtime, on a clean .txt scan:
Metric lewrep2 ripgrep (rg) Verdict Total Process Time 0.052s 0.068s lewrep2 is ~23% faster Memory Footprint 2.56 MB 6.09 MB lewrep2 uses <50% RAM

# Why lewrep2 Wins

• Production‑grade engine room — powered by the same crates that make ripgrep fast. 
• Zero‑copy architecture — optional OS‑native memory mapping streams file chunks directly. 
• Smart traversal — the ignore crate respects .gitignore and skips noise directories. 
• Parallel execution — driven by a Rayon thread pool for maximum throughput.

# 🧠 Architecture Overview

Core Components
• grep‑searcher — high‑performance line scanning 
• grep‑regex — fast, compiled regex engine 
• ignore — directory traversal + .gitignore logic 
• Rayon — parallel work‑stealing scheduler

Pipeline Flow
1. Walk filesystem with ignore rules
2. Dispatch file chunks to Rayon workers
3. Stream data via mmap or buffered IO
4. Execute regex engine
5. Emit results with minimal formatting overhead

# ⚙️ Features & Flags

Basic Usage
lewrep2 [path]

Flags
• -i, --ignore-case    — case‑insensitive search 
• -n, --line-number    — show line numbers 
• -v, --invert-match   — select non‑matching lines 
• -c, --count          — suppress normal output; print a count of matching lines per file
• -l                   — filenames‑only mode (short‑circuits instantly on match) 
• -I                   — custom ignore overrides 
• -A                   — show trailing context lines 
• -u                   - shows hidden files (-u), open .gitignore (-uu) & binary files                           (-uuu) 

Pipeline‑Friendly
Fully compatible with:
• grep • ripgrep • sed • awk • cat • tree • ls

lewrep2 behaves like a classic UNIX tool — predictable, composable, script‑friendly.

# 🧪 Philosophy: What lewrep2 Prioritises

• Speed over features 
• Determinism over magic 
• Clarity over complexity 
• Parallelism over sequential bottlenecks 
• Open‑source transparency

# 🐛 Bug Reports

Found a bug? Open an Issue on GitHub so it can be patched quickly.
lewrep2 is actively maintained and performance‑tuned.

# 💡 Contributions

Pull Requests are welcome — especially around:
• performance improvements • new flags • traversal optimizations • documentation enhancements

Lewrep2 is open source meaning its free to use, download, modify, community patches, upgrade features.

# 📄 License

MIT License — simple, permissive, developer‑friendly.

# 🦀 Developed by xlewis1

Built with Rust, engineered with intent, and optimized with care.
