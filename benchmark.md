---
layout: default
---

# Benchmark Instances
The benchmark instances we used in our experiments came from a combination of sources, including the [SAT Competition](http://www.satcompetition.org/), [Hardware Model Checking Competition](http://fmv.jku.at/hwmcc/), and various instance generators.
We outline the benchmark instances for each category in detail here:

## Agile:
For this category, we take instances from the <span style="font-variant:small-caps;">Agile</span> track of the SAT competition:
* [SAT Competition 2016](https://baldur.iti.kit.edu/sat-competition-2016/index.php?cat=downloads)
* [SAT Competition 2017](https://baldur.iti.kit.edu/sat-competition-2017/index.php?cat=downloads)
  
## Verification:
For this category, we take instances from the <span style="font-variant:small-caps;">Verification</span> track of the SAT competition:
* c_bounded_model_checker from [SAT Competition 2018](http://www.satcompetition.org/)
* industrial_combinational_equivalence from [SAT Competition 2016](https://baldur.iti.kit.edu/sat-competition-2016/index.php?cat=downloads)
* tools_driven_by_sat_solvers from [SAT Competition 2016](https://baldur.iti.kit.edu/sat-competition-2016/index.php?cat=downloads)
* rolling instances from [HWMC Competition 2019](http://fmv.jku.at/hwmcc19/#benchmarks)

We also generate scaled versions of the rolling instances from the HWMC Competition, using [abc](https://people.eecs.berkeley.edu/~alanmi/abc/).
* for each base `.aig` instance, we unroll it 3, 6, 9, 12, 15, 17, 18, 19, 20, 21 and 22 times to get 11 instances
* an example of unrolling 22 times: `./abc -c "&read example.aig; &put; fold; frames -i -F 22; &get; &write_cnf example_unroll22.cnf" `

## Crypto:
For this category, we take instances from the <span style="font-variant:small-caps;">Crypto</span> track of the SAT competition:
* bitcoin_mining from [SAT Competition 2018](http://www.satcompetition.org/)
* logical_cryptanalysis_hash_function from [SAT Competition 2018](http://www.satcompetition.org/)

We also generate CNF encodings of the SHA1 and SHA256 preimage problems using [this SAT encoding tool](https://github.com/saeednj/SAT-encoding) and vary them by randomly restricting their input bits.
* SHA1: we generate one instance per round from 18 rounds to 80 rounds for each of the three operators (dot_matrix, counter_chain, two_operand) supported by the generator.
* SHA256: we generate one instance per round from 18 rounds to 64 rounds for each of the three operators (dot_matrix, counter_chain, two_operand) supported by the generator.
* For each of the instances generated, we apply a random restriction to the input bits to SHA; we restrict from 440 bits to 510 bits with a step size of 5 bits. The intention of the restriction is to get solvable crypto instances for higher numbers of rounds.
	
## Crafted:
For this category, we take instances from the <span style="font-variant:small-caps;">Crafted</span> track of the SAT competition:
* community_attachment from [SAT Competition 2016](https://baldur.iti.kit.edu/sat-competition-2016/index.php?cat=downloads)
* crafted_combinational_equivalence from [SAT Competition 2017](https://baldur.iti.kit.edu/sat-competition-2017/index.php?cat=downloads)
* grandtour_puzzle from SAT Competition 2018
* popularity_similarity from [SAT Competition 2017](https://baldur.iti.kit.edu/sat-competition-2017/index.php?cat=downloads)
* k_colorability from SAT Competition 2018
* sorting_networks from [SAT Competition 2016](https://baldur.iti.kit.edu/sat-competition-2016/index.php?cat=downloads)
* polynomial_multiplication from [SAT Competition 2018](http://www.satcompetition.org/)
* unit_distance_graph_chromatic_number from [SAT Competition 2018](http://www.satcompetition.org/)

We also generate instances using [cnfgen](https://massimolauria.net/cnfgen/):
* counting_principle - m:{10-14} n:{3-8} where m > n 
* ordering_principle - n: {10-99}
* parity - n: {11-99}
* php - m:{10-91} n:{9-87} where m > n
* Tseitin - n: {100-1000} for 3, 4, 5, 6 regular graphs
* Tseitin_grid - m:{10-100} n:{9-96} where m > n
    
## Random:
For this category, we take instances from the <span style="font-variant:small-caps;">Random</span> track of the SAT competition:
* k_sat_q_planted from [SAT Competition 2018](http://www.satcompetition.org/)

We also generate instances using [cnfgen](https://massimolauria.net/cnfgen/):
* 3-CNF instances from n=1000 to n=20000 with a step size of 50; we use CVR 4.26
* 5-CNF instances from n=1000 to n=10000 with a step size of 50; we use CVR 21.12
* 7-CNF instances from n=1000 to n=5200 with a step size of 50; we use CVR 87.79
