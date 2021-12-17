### ΒΗΜΑ 1:

| Name        | system.cpu.committedInsts | system.cpu.dcache.replacements | system.l2.overall_accesses::total |
| ----------- | ----------- | ----------- | ----------- |
| specbzip | 100000001 | 710569 | 712341 |
| spechmmer |	100000000	| 65718 |	70563 |
| speclibm | 100000000 | 1486955 | 1488538 |
| specmcf | 100000001 | 54452 |	724390 |
| specsjeng	| 100000000 | 5262377 |	5264051 |

Αν το gem5 δε μας έδινε το συνολικό αριθμό των accesses στην l2 cache, θα μπορούμε να τον υπολογίσουμε αθροίζοντας τα misses στο l1d cache και l1i cache.

| Name | sim_seconds |	CPI		| L1D_miss_rate	| L1I_miss_rate	| L2_miss_rate |
|------|-------------|--------|---------------|---------------|--------------|
|specbzip	|0.083982	|1.679650	|0.014798|	0.000077|	0.282163|
|spechmmer|	0.059396	|1.187917	|0.001637|	0.000221	|0.077760|
|speclibm|	0.174671	|3.493415|	0.060972|	0.000094	|0.999944|
|specmcf	|	0.064955	|1.299095|	0.002108|	0.023612|	0.055046|
|specsjeng	|0.513528|	10.270554|	0.121831	|0.000020	|0.999972|


### ΒΗΜΑ 2:

BZIP:
|Benchmarks|	system.cpu.cpi|	system.cpu.dcache.overall_miss_rate::total|	system.cpu.icache.overall_miss_rate::total|	system.l2.overall_miss_rate::total|
|---|---|---|---|---|
|specbzip_0|	1.595869|	0.008747|	0.000078|	0.702900|
|specbzip_1|	1.595869|	0.008747	|0.000078	|0.702900|
|specbzip_2	|1.724184	|0.021384|	0.000078	|0.271750|
|specbzip_3|	1.588198|	0.007669|	0.000055	|0.587973|

HMMER:
|Benchmarks	|system.cpu.cpi	|system.cpu.dcache.overall_miss_rate::total|	system.cpu.icache.overall_miss_rate::total	|system.l2.overall_miss_rate::total|
|---|---|---|---|---|
|spechmmer_0	|1.232977	|0.005675	|0.000404	|0.022744|
|spechmmer_1|	1.186575|	0.002018|	0.000403|	0.060586|
|spechmmer_2	|1.183838	|0.000662	|0.000402	|0.171604|
|spechmmer_3|	1.178979|	0.000367|	0.000385|	0.150107|

LBM:
|Benchmarks	|system.cpu.cpi	|system.cpu.dcache.overall_miss_rate::total|	system.cpu.icache.overall_miss_rate::total	|system.l2.overall_miss_rate::total|
|---|---|---|---|---|
|speclbm_0	|2.650259	|0.062151	|0.000097	|0.973317|
|speclbm_1|	2.619860	|0.061119	|0.000097	|0.996771|
|speclbm_2	|2.617348	|0.060971	|0.000097	|0.999931|
|speclbm_3	|2.003465|	0.030487|	0.000107|	0.999827|

MCF:
|Benchmarks	|system.cpu.cpi	|system.cpu.dcache.overall_miss_rate::total|	system.cpu.icache.overall_miss_rate::total	|system.l2.overall_miss_rate::total|
|---|---|---|---|---|
|specmcf_0|	1.176616|	0.006983	|0.000042	|0.214748|
|specmcf_1|	1.145325|	0.002399|	0.000042|	0.734230|
|specmcf_2|	1.142315	|0.001877	|0.000042|	0.917136|
|specmcf_3|	1.117395	|0.001120|	0.000034	|0.850487|


SJENG:
|Benchmarks	|system.cpu.cpi	|system.cpu.dcache.overall_miss_rate::total|	system.cpu.icache.overall_miss_rate::total	|system.l2.overall_miss_rate::total|
|---|---|---|---|---|
|specsjeng_0	|7.061276	|0.122441|	0.000020|	0.990081|
|specsjeng_1|	7.041190|	0.121831|	0.000020|	0.999975|
|specsjeng_2	|7.191998	|0.121830	|0.000020	|0.999985|
|specsjeng_3|	4.934884|	0.060917|	0.000014|	0.999967|
