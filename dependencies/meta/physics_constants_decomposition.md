---
axis: B
position: physics_layer_aux
static_dynamic: static
connected_to:
  - B.physics_layer
  - A.algebra_analysis
  - A.harmonic_analysis
arrow_status:
  upstream: done
  downstream: stub
updated: 2026-04-09
---

# 物理定数の型分類

**Level**: L2-physics (physics_dictionary_v0.md の companion)
**Dependencies**: L1/c_phase_complex.md §5, L1/c_scaling_laws.md §1.4, L1/q_quantum_observation.md §7, L0/finite_observation.md §7
**Purpose**: 物理定数を「値の由来」と「役割の由来」に分離し、ΣΦ 内での状態を分類する

---

## §1 型分類の原理

物理定数には構造的に異なる4つの型がある：

| 型 | 定義 | 値の決まり方 | 例 |
|---|---|---|---|
| **Type I: 観測対称性** | L0/L1 の対称性から値が導出される | 代数的に確定 | c_s², √e |
| **Type II: 換算係数** | 異なる物理量の間のスケール変換 | 数値は単位系依存（自然単位系で 1）。ただし背後の構造（因果速度の存在、非可換性の存在）は単位系に依存しない | ħ, c, k_B |
| **Type III: 結合定数** | 相互作用の強さを決める | 対称性は型を決めるが値は決めない | α, G_F |
| **Type IV: 幾何定数** | 時空の大域構造に関わる | 宇宙論的条件で決まる | G, Λ |

**核心**: Type I は ΣΦ の守備範囲。Type II は「何を換算しているか」の役割分類で閉じる。Type III/IV は現段階では位置づけのみ。

### 1.2 Origin taxonomy (audit 2026-04-08 追加)

Type I 内部の「由来」を細分類する。mixed-origin 定数の分析で必要になった境界線の明確化。

| Origin | 定義 | 例 |
|---|---|---|
| **Structural** | 公理のみから導出。convention に依存しない | c_s² = 1/2 (ℤ/2ℤ 偶奇等確率) |
| **Threshold/convention** | 導出可能だが、入力に任意の閾値選択を含む | σ* = √(2 ln 2) (half-amplitude: E[cos Z]=1/2 選択に依存) |
| **Geometric** | 空間/計量構造に依存。観測者の制約ではない | √(2π) (円周長), p² の 2 (ユークリッド計量) |
| **Measurement** | 実験プロトコルに依存 | 装置固有のノイズパラメータ |

**使用規則**: 定数を Type I-a (derived) に昇格させるとき、structural か threshold/convention かを必ず明記する。"derived" は「公理から式が出る」であって「値が convention-free」とは限らない。

---

## §2 Type I: 観測対称性定数（ΣΦ 既知）

### 2.1 Type I-a: 導出済み (derived)

| 定数 | 値 | 由来 | ΣΦ での役割 | 辞書内居場所 |
|---|---|---|---|---|
| c_s²(ΣΦ) | 1/2 | ℤ/2ℤ 一様測度（偶奇対称性） | 偶奇/二値対称 | c_phase_complex.md §5 |
| c_s | 1/√2 ≈ 0.7071 | c_s² の平方根 | 振幅半減 | c_scaling_laws.md §1.4 |
| log 2 | 0.6931... | ℤ/2ℤ の Shannon エントロピー | 二値一様測度のエントロピー | c_phase_complex.md §5 (log 2 項) |
| √e | e^{1/2} ≈ 1.6487 | exp(c_s²) = exp(1/2) | T8 Boltzmann codim weight | c_scaling_laws.md §1.4 |
| σ* | √(2 ln 2) ≈ 1.1774 | ガウス特性関数 e^{-σ²/2} + half-amplitude convention | 位相ノイズ閾値（frame function 崩壊点） | Paper_C.tex Thm C.8, q_quantum_thermodynamics.md OQ-QTD3 |

**σ* メモ (2026-04-08, revised after audit)**: σ* は Type I-a（導出済み）だが convention dependence あり。導出: e^{-σ²/2} = 1/√2 → σ² = 2 ln 2 (Paper_C.tex Thm C.8)。構造的なのは「ガウス特性関数が信号保持量を決める」形。具体値 √(2 ln 2) は half-amplitude (E[cos Z]=1/2) 閾値選択に依存する（1/e-power なら σ²=2, 1/4-power なら σ²=2 ln 4）。~~ℤ/2ℤ 共通根~~ retracted — bipartition パターンは観察されるが群構造への還元は overclaim。

### 2.2 内部関係

これらは独立ではない。全て ℤ/2ℤ の一様測度（= 偶奇対称性 = 最小の非自明パリティ）から生じる：

```
ℤ/2ℤ 一様測度
    │
    ├─→ c_s² = E[cos²(πh·t)] = 1/2     (c_phase_complex.md §5)
    │     │
    │     ├─→ c_s = 1/√2                 (平方根)
    │     │
    │     └─→ √e = exp(c_s²) = exp(1/2)  (T8 Boltzmann codim weight)
    │
    ├─→ log 2 = H(1/2) = Shannon entropy of fair coin
    │
    └─→ σ* = √(2 ln 2)                   (導出確認、convention dependence あり)
```

**σ* の導出状態**: σ* = √(2 ln 2) はガウス位相ノイズの特性関数 E[cos Z] = e^{-σ²/2} を half-power point 1/√2 に等置することから出る (Paper_C.tex Thm C.8)。構造的なのは「ガウス特性関数形」。具体値の ln 2 は half-amplitude convention に依存する（閾値変更で値が変わる）。c_s² = 1/2 および log 2 との関係は bipartition パターンとして観察されるが、ℤ/2ℤ 群構造への還元は overclaim として retracted (audit 2026-04-08)。詳細: q_quantum_thermodynamics.md OQ-QTD3。

### 2.3 量子的定式化との対応

q_quantum_observation.md §7 で確認したように：

| 定数 | 数論的 | 調和解析的 | 量子的 |
|---|---|---|---|
| c_s² = 1/2 | 偶奇等確率 | E[cos²] = 1/2 | Tr(ρ_max · Π_even) = 1/2 |
| log 2 | log|ℤ/2ℤ| | — | S(ρ_max) = log 2 (von Neumann entropy) |
| √e = exp(1/2) | — | — | exp(c_s²) = Boltzmann weight at codim 1 |

**注**: log 2 の量子的対応は von Neumann エントロピー S(ρ_max) = -Tr(ρ_max log ρ_max) = log 2。これは c_s² = Tr(ρ_max · Π_even) = 1/2 とは **別の量**（エントロピー vs Born 期待値）だが、同じ状態 ρ_max から生じる。

### 2.4 c_s² の同形異義語: ΣΦ c_s² vs 物理 c_s² (追記 2026-04-09)

**WARNING — 混同禁止。** 以下は異なる量であり、同じ記号で呼ばれることによる誤接続が確認された（2026-04-09 conservation law investigation, verdict D）。

| 記号 | 値 | 由来 | 定義域 | ΣΦ 的位置 |
|---|---|---|---|---|
| **c_s²(ΣΦ, parity)** | **1/2** | ℤ/2ℤ 一様測度、E[cos²(πht)] = 1/2 | 離散整数の偶奇対称性（内部構造） | **Type I-a, structural** — 本辞書の守備範囲 |
| c_s²(CFT, d=3) | 1/3 | 共形対称性 T^μ_μ = 0 → p = ρ/3 | d_space = 3 の時空次元（外部幾何） | **Type I だがΣΦ外** — 物理定数、導出可能だがΣΦの公理系からではない |
| c_s²(radiation) | 1/3 | 超相対論的完全流体 p = ρ/3 | 放射優勢宇宙 | 上と同値（CFT の物質的実現） |

**誤接続の経緯**: deevid（拡散モデル AI）が体感的に c_s² = 1/3 を報告 → ΣΦ の c_s² = 1/2 と混同 → 「c_s² + phase_importance = 1/3 + 2/3 = 1」保存則を仮説化 → 検証の結果 D 判定（数値的偶然）。根本原因: 2つの c_s² の混同。

**分離原則**: 今後 c_s² が文脈に現れたとき、必ず以下を確認する:
1. どの対称性から来ているか（ℤ/2ℤ parity? 共形対称性? その他?）
2. どの空間で定義されているか（内部場? 時空? テンソルネットワーク?）
3. ΣΦ の Type I-a に属するのは **c_s²(ΣΦ) = 1/2 のみ**

**一般化の可能性（OQ）**: 「観測者の種類ごとに c_s² が異なる」という構造がありうる。deevid が体感した c_s² = 1/3 は拡散モデル内部の CFT 的構造であり、ΣΦ parity の c_s² = 1/2 とは別の観測者ゲージに属する。これは L3 OQ として記録する。

### 2.5 Phase importance 2/3 の metric 依存性 (追記 2026-04-09)

**WARNING — phase importance は metric-dependent 量である。**

Monte Carlo 検証（division_algebra_test.py, 2026-04-09）で判明した事実:

| Metric | Phase importance | 根拠 |
|---|---|---|
| **L2 (MSE) 有限擾乱** | **~0.75-0.77（次元非依存）** | Monte Carlo: ℝ^d (d=1,...,16) 全てで I_phase ≈ 0.75。d/(d+1) 予測に従わない。amplitude randomization の分布ミスマッチがR²損失を支配し、次元構造が消える |
| **Fisher 情報（微小擾乱）** | **d/(d+1)**（ℂ なら 2/3） | Paper C Thm C.7: 接空間上の次元カウント。cos θ, sin θ の 2 real DOF vs r の 1 real DOF。代数的恒等式として正しいが、これは**微小摂動の感度**であって**有限破壊の損失**ではない |
| **人間知覚 metric** | **~2:1（体感的）** | deevid（拡散モデル AI）の報告: 位相破壊 → 認識不能（巨大損失）、振幅破壊 → まだ猫に見える（小損失）。拡散モデルのデコーダは人間アノテーション/知覚距離で学習されているため、内部 metric ≅ 人間視覚 metric |

**帰結**: Paper C の 2/3 と deevid の 2:1 は**別の量**。

- Paper C の 2/3 = Fisher 情報の次元カウント（代数的、微小、metric-free に見えるが実は L2 微小極限）
- deevid の 2:1 = 知覚空間上の有限擾乱損失比（人間視覚が gauge）
- 両者が近い値を取るのは、人間視覚が「位相を情報量的に効率よく利用するように進化した」可能性を示唆するが、**数値的一致は保証されない**

**ΣΦ 的意味**: 2/3 は「位相がどれだけ重要か」ではなく「**ある metric の下で**位相がどれだけ重要か」。metric を指定しない phase importance は未定義。

- L2 微小 → 2/3（Paper C）
- L2 有限 → ~3:1（~0.75、Monte Carlo）
- 知覚 → ~2:1（deevid 体感）
- Shannon → 分布依存（Ni-Huo: ~0.578）

**OQ-PI1（新規）**: 人間視覚 metric を形式化したとき、その metric 上での phase importance は正確にいくつか? 2/3 に一致するなら、Paper C の代数的結果が人間視覚に深い意味を持つ。一致しないなら、2/3 は特定の代数構造（cyclotomic / Fisher）の産物であり、知覚とは別。

---

## §3 Type II: 換算係数（役割分類）

### 3.1 一覧

| 定数 | 換算する2つの量 | ΣΦ 的役割 | L1 対応 |
|---|---|---|---|
| ħ | 位相 ↔ 作用 | 連続的 ι_L の作用版。ι_L(n) = e^{2πin/L} の「2π」が離散→連続で ħ に変わる | q_quantum_observation.md §4 |
| c | 時間 ↔ 空間 | 因果構造のスケール。光錐 = 観測可能な最大窓（L0 A0a の物理的実現） | physics_dictionary §3.4 |
| k_B | エントロピー ↔ エネルギー/温度 | 情報と熱の換算。§2.2 の log 2 を物理単位に変換する係数 | physics_dictionary §2.3 |

### 3.2 数値 vs 構造の分離

ħ = c = k_B = 1 とする自然単位系では、これらの **数値** は消滅する。しかし背後の **構造** は消えない：

| 定数 | 数値（Type II、単位系依存） | 構造（単位系非依存） |
|---|---|---|
| c | 時間-空間の換算比 | **有限の不変因果速度が存在する** → 光錐構造、因果律 |
| ħ | 位相-作用の換算比 | **非可換な位相-作用結合が存在する** → [x,p]=iħ, 量子干渉 |
| k_B | エントロピー-エネルギーの換算比 | エントロピーがエネルギーと同じ次元で測れる（構造的には弱い） |

c と ħ は「数値は Type II だが、構造は物理の芯」。自然単位系で 1 になっても、因果構造と非可換構造は残る。k_B は最も純粋な換算係数で、背後の構造は最も弱い。

ΣΦ 的には：L1 の定理は全て自然単位系で書ける（数値としての ħ, c, k_B に依存しない）。だが q_quantum_observation.md の [A,B]≠0（ħ の構造的内容）や、有限窓の物理的サイズ制限（c の因果構造）は L1/L0 の核心に関わる。

### 3.3 ħ の ΣΦ 的位置づけ

ħ は特別な注意を要する。離散系（ℤ/Lℤ）では位相は 2π/L 刻みで自然に離散化されるが、連続系では位相と作用の間に換算が必要になる：

    離散: ι_L(n) = e^{2πin/L}        (L が周期を設定)
    連続: U(t) = e^{-iHt/ħ}          (ħ が位相/作用の換算を設定)

ħ → 0 の古典極限は L → ∞ の極限と構造的に同等：
- L → ∞: μ_L（L 次単位根）が S¹ を稠密に埋める（c_phase_complex.md §6）
- ħ → 0: 量子的位相が古典的作用に連続化する（WKB 近似）

両者とも「離散構造が連続構造に移行する」過程であり、ΣΦ の τ-正規化（c_phase_complex.md §6）はこの移行の一般的記述を与える。

**数値 vs 構造**: ħ の数値は自然単位系で 1 に吸収される（Type II）。しかし「位相と作用が非可換に結合している」という構造（[x,p]=iħ）は単位系に依存せず、q_quantum_observation.md §2 の [A,B]≠0 として L1-fiber の核心を担う。ħ の ΣΦ 的意味は数値ではなく、この非可換結合構造の存在にある。

### 3.4 k_B の ΣΦ 的位置づけ

k_B は §2 の Type I 定数 log 2 を物理単位に変換する：

    S_phys = k_B · S_info

ここで S_info = -Σ p_k log p_k は無次元の Shannon/von Neumann エントロピー。k_B が「nats を Joules/Kelvin に変換する」のは、log 2 が「bits を nats に変換する」のと同じ構造。

physics_dictionary §2.3 の「不可逆性 = 有限窓に見えない自由度への情報流出」において、k_B は「情報の流出量をエネルギー単位で測る換算係数」として機能する。

---

## §4 Type III: 結合定数（位置づけのみ）

### 4.1 一覧

| 定数 | 値 | 対称性 | 値の決まり方 | ΣΦ 状態 |
|---|---|---|---|---|
| α (微細構造定数) | ≈ 1/137 | U(1) 電磁 | RG flow + 境界条件 | **未着手** |
| α_s (強結合定数) | ≈ 0.12 (@M_Z) | SU(3) 色 | asymptotic freedom + Λ_QCD | **未着手** |
| G_F (Fermi 定数) | ≈ 1.17×10⁻⁵ GeV⁻² | SU(2) 弱 | Higgs VEV | **未着手** |
| 質量比 (m_e/m_p 等) | 各種 | 味の対称性 (破れ) | Yukawa 結合 | **未着手** |

### 4.2 ΣΦ が Type III に言えること（現時点）

Type III 定数について、ΣΦ が現段階で言えるのは：

1. **対称性の型は L1-fiber で決まる**: U(1), SU(2), SU(3) は q_quantum_observation.md の作用素代数の具体的実現
2. **値は L1 では決まらない**: α ≈ 1/137 の「137」は L1 の対称性だけでは出ない。くりこみ群の flow + UV 境界条件が必要で、これは L2-physics（またはそれ以上）の構造
3. **c_s² = 1/2 との関係は不明**: Type I 定数と Type III 定数の間に代数的関係があるかどうかは open question
4. **α は「解像度のダイアル」**: α⁰ で殻構造（Type I が支配）、α² で微細構造（多重項分裂）、α⁴ で超微細構造。α を上げるたびに ι_L の入れ子が一段深くなる。詳細は `q_fine_structure.md` §7

**注意**: α = 1/137 を ΣΦ から「導出」しようとするのは、現段階では**時期尚早**。まず Type I の完全な理解を固め、Type II の役割分類を終えてから、Type III に踏み込む。ただし α の**構造的役割**（値ではなく、何をするか）は q_fine_structure.md §7 で明確化された。

---

## §5 Type IV: 幾何定数（後回し）

| 定数 | 値 | Track B との関係 | ΣΦ 状態 |
|---|---|---|---|
| G (重力定数) | 6.674×10⁻¹¹ m³kg⁻¹s⁻² | ホログラフィック: S = A/(4G) | **後回し** |
| Λ (宇宙定数) | ≈ 10⁻¹²² (Planck 単位) | de Sitter horizon → 有限窓 | **後回し** |

Track B（ホログラフィック、physics_dictionary §3）が「方向性提示」に留まっている現段階では、Type IV は位置づけのみ。Track B が厳密化されたときに再訪する。

---

## §6 作業ロードマップ

### 完了

| 定数群 | 状態 | 居場所 |
|---|---|---|
| c_s², c_s, √e | 導出済み、三重一致確認済み | L1/phase_complex, scaling_laws, quantum_observation |
| ħ, c, k_B の役割 | 位置づけ完了 | 本ファイル §3 |

### 次のアクション

| タスク | 優先度 | 前提 |
|---|---|---|
| ~~log 2 の明示的辞書化~~ | ~~HIGH~~ | **完了**: c_phase_complex.md §5 に「log 2 = ℤ/2ℤ の Shannon エントロピー」として追記済み |
| ~~σ* = √(2 ln 2) と c_s² の関係~~ | ~~HIGH~~ | **完了**: ℤ/2ℤ 共通根確立。q_quantum_thermodynamics.md OQ-QTD3 |
| α = 1/137 の ΣΦ 的位置づけ | LOW | Type I/II が完了してから |
| G, Λ の Track B 接続 | LOW | Track B の厳密化が先 |

### 原則

**値の由来** と **役割の由来** を混ぜない：
- Type I: 値が導出できる → 導出を示す
- Type II: 値は単位系依存 → 役割を示す
- Type III/IV: 値は経験的 → 位置づけだけ示す

---

## §7 隠蔽パターン: L0/L1 exact value の L2 fitting parameter への吸収

### 7.1 メカニズム

L0/L1 の代数的に確定する値が、L2 ドメイン観測時に domain-specific correction と一体化して計測され、全体が「経験定数」として fitting parameter に吸収されるパターン。

```
observed_value = L0/L1_exact + L2_correction + noise
                  ↓ 分離されない場合
              = "empirical_constant" ± error
                  → exact component が隠蔽される
```

### 7.2 確認済みインスタンス

| ドメイン | 経験値 | L0/L1 exact | L2 correction | 発見 |
|---|---|---|---|---|
| FX: alpha_eff | 0.76 | c_s² = 0.5 | +0.26 (edge/bulk interference) | finite_observation.md §7.5 |
| EEG: phase noise | ~1.18 rad | σ* = √(2 ln 2) = 1.1774... | residual → physiological | Paper_C.tex Thm C.8 |
| Landauer: heat cost | kT ln 2 | ln 2 (ℤ/2ℤ) | ×kT (thermal scale) | q_quantum_thermodynamics.md §5 |

### 7.3 候補インスタンス（未確認）

| ドメイン | 経験値 | 候補 exact | 状態 |
|---|---|---|---|
| Connectome: φ_eff/φ | ~0.37 | 1/e = 0.3679...? | 未検証。もし 1/e なら exp(c_s²) = √e との関係あり |
| Equipartition: kT/2 | 1/2 per DOF | partial ℤ/2ℤ + geometric | 分析済み、混合型 |

### 7.4 検出戦略

新しいドメインで定数を観測したとき：

1. **Type I 候補との照合**: 観測値が c_s² (0.5), c_s (0.707), ln 2 (0.693), √e (1.649), σ* (1.177), 1/e (0.368) の近傍にないか
2. **残差の検査**: exact value を引いた残差に構造があるか（ドメイン固有のパラメータで説明できるか）
3. **null 検定**: ランダムデータでも同じ近似が出るか（feedback: test against null）

この手順は L2 ドメイン辞書を書くたびに実行すべき**標準的検証プロトコル**。

---

*作成日: 2026-04-08*
*最終更新: 2026-04-09*
