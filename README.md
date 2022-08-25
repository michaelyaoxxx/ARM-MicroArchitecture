# ARM-MicroArchitecture
compare microarchitecture of ARMv7 &amp; ARMv8 Application Processor

# ARMv7-A Processor Comparison Table
## Image Format
![Comparison Table](https://github.com/michaelyaoxxx/ARM-MicroArchitecture/blob/main/ARMv7-A%20Processor%20Comparison%20Table.png)

## Original Format

| Feature                      | Feature                                                      | Cortex-A5                               | Cortex-A7                                | Cortex-A8                                                    | Cortex-A9                                                    | Cortex-A15                                                   | Cortex-A17                                                   |
| ---------------------------- | ------------------------------------------------------------ | --------------------------------------- | ---------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| General Information          | announced  date                                              | 2009                                    | 2011                                     | 2005                                                         | 2007                                                         | 2010                                                         | 2014                                                         |
| General  Information         | Release  date                                                | Dec  2009                               | Oct  2011                                | July  2006                                                   | March  2008                                                  | April  2011                                                  | June  2013                                                   |
| General  Information         | Type                                                         | low power                               | low power                                | main stream                                                  | main stream                                                  | High  Performance                                            | main stream                                                  |
| General  Information         | CPU Team                                                     | Cambridge                               | Cambridge                                | Austin                                                       | Sophia-Antipolis                                             | Austin                                                       | Sophia-Antipolis                                             |
| General  Information         | Typical  clock speed                                         | ~1GHz                                   | ~1.5GHz  on 28nm                         | ~1GHz  on 65nm                                               | ~2GHz  on 40nm                                               | ~2.5GHz  on 28nm                                             | 2.5GHz+  on 28nm                                             |
| General  Information         | Multicore                                                    | 1-4  cores                              | 1-4  cores                               | 1  core                                                      | 1-4  cores (Single core version also available?)             | 1-4  cores (Single core version also available?)             | 1-4  cores                                                   |
| PPA                          | Peak  integer throughput(DMIPS/MHz)                          | 1.6                                     | 1.9                                      | 2                                                            | 2.5                                                          | 3.5                                                          | 3.2?                                                         |
| PPA                          | power                                                        | ~80mw  1/3 of A9                        | 100mW                                    | <=300mW                                                      | <  250 mW@1Ghz                                               | 500  mw?                                                     | 200mW                                                        |
| PPA                          | Performance  boost                                           | 相当于A9性能的75%                       | 相比A8，提升2倍                          | base                                                         | 相对于A8，单核提升50%                                        | 相比A9，单核提升40%                                          | 相比A9，单核提升60%，相比A12提升40%                          |
| PPA                          | Area                                                         | 0.2 mm^2                                | 0.45mm^2?                                | 3mm^2?                                                       | <=1.5  mm2^2?                                                | 3mm^2                                                        | 1.93  mm^2                                                   |
| PPA                          | Process                                                      | 40nm                                    | 40nm/28nm                                | 65nm/45nm                                                    | 40nm                                                         | 32/28nm                                                      | 28nm                                                         |
| Main  Extensions Information | Floating  Point Unit                                         | Optional                                | Yes                                      | Yes                                                          | Optional                                                     | Optional                                                     | Optional                                                     |
| Main  Extensions Information | Half  precision extension(16bit)                             | Yes                                     | Yes                                      | No                                                           | Yes                                                          | Yes                                                          | Yes                                                          |
| Main  Extensions Information | Hardware  division                                           | No                                      | Yes                                      | No                                                           | No                                                           | Yes                                                          | Yes                                                          |
| Main  Extensions Information | Hardware  Fused Multiply-Accumulate                          | Yes                                     | Yes                                      | No                                                           | No                                                           | Yes                                                          | Yes                                                          |
| Main  Extensions Information | LAPE  Extensions(40bit)                                      | No                                      | Yes                                      | No                                                           | No                                                           | Yes                                                          | Yes                                                          |
| Main  Extensions Information | Virtualization  Extensions                                   | No                                      | Yes                                      | No                                                           | No                                                           | Yes                                                          | Yes                                                          |
| Main  Extensions Information | big.LITTLE                                                   | No                                      | LITTLE(big:A15/A17)                      | No                                                           | No                                                           | Big(little:  A7)                                             | Big(little:  A7)                                             |
| Main  Extensions Information | VFP  architecture                                            | VFPv4                                   | VFPv4                                    | VFPv3                                                        | VFPv3                                                        | VFPv4                                                        | VFPv4                                                        |
| Main  Extensions Information | NEON  architecture                                           | NEON                                    | NEONv2                                   | NEON                                                         | NEON                                                         | NEONv2                                                       | NEONv2                                                       |
| Pipieline                    | Execution  order                                             | In  order                               | In  order                                | In  order                                                    | Out  of order                                                | Out  of order                                                | Out  of order                                                |
| Pipieline                    | Pipeline  stages                                             | 8                                       | 8                                        | 13-stage  (main integer pipeline)     10-stage (NEON media pipeline) | 9-12  stages                                                 | 15+                                                          | 11+                                                          |
| Pipieline                    | Instructions  decoded per cycle                              | 1                                       | Partial  dual-issue                      | 2  (Superscalar)                                             | 2  (Superscalar)                                             | 3  (Superscalar)                                             | 2  (Superscalar)                                             |
| BPU                          | BTAC(BTB)                                                    | 4-entry  BTAC                           | •  A 4-entry BTIC.     • A 8-entry BTAC. | 512-entry  2-way set associative BTB                         | a  2-way BTAC, implemented in RAMs 512-4096 entry            | 2-level  dynamic predictor with BTB     (256-entry, micro BTB 64-entry?) | 2K  or 4K entries BTAC                                       |
| BPU                          | Branch  pattern history table     /GHT(Global History Table) | 256-entry  branch pattern history table | 256-entry  branch pattern history table  | 512-entry  2-way set associative GHB                         | 1024,  2048, 4096, 8192 or 16384 2-bit GHB                   | 2-level  global history-based direction predictor            | two-level  GHB(size?)                                        |
| BPU                          | Other  predictor component                                   | -                                       | -                                        | -                                                            | -                                                            | •  Static branch predictor     • Indirect predictor          | •  Static branch predictor                                   |
| BPU                          | Return stack                                                 | 4-entry                                 | 8-entry                                  | 8-entry                                                      | 8-entry                                                      | 48-entry                                                     | 48-entry(Nested)                                             |
| MMU-TLB                      | Micro-TLB/L1  TLB(Instr. & Data)                             | 10-entry                                | 10-entry                                 | 32-entry                                                     | 32-entry                                                     | 32-entry  fully-associative                                  | dTLB:  32-entry, full-associative     iTLB: 32/64/48-entry, full-associative |
| MMU-TLB                      | Main-TLB                                                     | 128-entry  two-way set-associative      | 256-entry  two-way set-associative       | ?                                                            | •fully-associative,  lockable array of four elements     •2-way associative,64-512 entry | 512-entry  4-way set-associative                             | 1024  entry 4-way set-associative                            |
| Cache                        | D$  Implementation                                           | PIPT                                    | PIPT                                     | PIPT                                                         | PIPT                                                         | PIPT                                                         | PIPT                                                         |
| Cache                        | I$  Implementation                                           | VIPT                                    | VIPT                                     | VIPT                                                         | VIPT                                                         | PIPT                                                         | VIPT                                                         |
| Cache                        | L1  I$ Size(KB)                                              | 4-64                                    | 8-64                                     | 16/32                                                        | 16-64                                                        | 32                                                           | 32/64                                                        |
| Cache                        | L1  D$ Size(KB)                                              | 4-64                                    | 8-64                                     | 16/32                                                        | 16-64                                                        | 32                                                           | 32                                                           |
| Cache                        | L1  I$ Structure                                             | 2-way  set associative                  | 2-way  set associative                   | 4-way  set associative                                       | 4-way  set associative                                       | 2-way  set associative                                       | 4-way  set associative                                       |
| Cache                        | L1  D$ Structure                                             | 4-way  set associative                  | 4-way  set associative                   | 4-way  set associative                                       | 4-way  set associative                                       | 2-way  set associative                                       | 4-way  set associative                                       |
| Cache                        | L1  D$ linefill buffer size(Bytes)                           | 2*16                                    | 2  * 32                                  | ?                                                            | 2  * 32                                                      | ?                                                            | 64                                                           |
| Cache                        | L1  D$ eviction buffer size(Bytes)                           | 32                                      | 64                                       | ?                                                            | 32                                                           | ?                                                            | 64                                                           |
| Cache                        | L1  D$ store buffer size(Bits)                               | 4-entry,  64                            | 4-entry,  64                             | ?                                                            | 4-entry,  64                                                 | ?                                                            | 8-entry,  64                                                 |
| Cache                        | Replacement  policy(L1I$/L1D$)                               | Pseudo  random / Pseudo random          | Pseudo  random / Pseudo random           | Pseudo  random / Pseudo random                               | pseudo  round-robin or pseudo random / pseudo random         | LRU  / LRU                                                   | Pseudo  random /Pseudo random                                |
| Cache                        | L2$  Structure                                               | ?                                       | 8-way  set associative                   | 8-way  set associative                                       | ?                                                            | 16-way  set associative                                      | 16-way  set associative                                      |
| Cache                        | L2  Cache                                                    | External  L2C-310                       | Integrated                               | Integrated                                                   | External  L2C-310                                            | Integrated                                                   | Integrated                                                   |
| Cache                        | L2  Cache size(KB)                                           | -                                       | 128-1024                                 | 0-1024                                                       | -                                                            | 512-4096                                                     | 256-8092                                                     |
| Cache                        | Cacheline  size(I$/D$, Bytes)                                | 32/32                                   | 32/64                                    | 64/64                                                        | 32/32                                                        | 64/64                                                        | 64                                                           |
| Cache                        | ECC                                                          | None                                    | None                                     | L2  ECC                                                      | None                                                         | Optional  for L1 and L2                                      | L1  None, L2 ECC                                             |
| others                       | ACP                                                          | Optional                                | No                                       | No                                                           | Optional                                                     | Optional                                                     | Optional                                                     |
| others                       | Generic  Timer                                               | No                                      | Yes                                      | No                                                           | Private  & Global Timer                                      | Yes                                                          | Yes                                                          |
| others                       | Interrupt  Controller                                        | Integrated  GIC v1 (MP only) , GIC-390  | Optional  Integrated GIC v2, GIC-400     | Not  include                                                 | Integrated  GIC v1 (MP only) , GIC-390                       | Optional  Integrated GIC v2, GIC-400                         | Optional  Integrated GIC v2                                  |
| others                       | Bus  Protocol                                                | AMBA3  AXI 64                           | AMBA  4 ACE 128-bit                      | AMBA3  AXI 64 or 128-bit                                     | AMBA3  AXI 2*64                                              | ACE  or CHI, 128-bit                                         | ACE,  128-bit                                                |
| others                       | Trace                                                        | Optional  ETM                           | Optional  ETM separate macrocell         | Integrated  ETM                                              | Integrated  PTM                                              | Integrated  PTM                                              | Integrated  PTM                                              |


