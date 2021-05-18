Dear Prof Lewis,

First, we would like to thank you, the Associate Editor, and the referees for reading our manuscript and providing comments and suggestions. The comments are very useful and we feel that the revision has improved our paper. We have carefully gone through every question and comment and addressed them in the revised submission. We provide a point-by-point response below.


### Reviewer 2

- The title is misleading as to the contents of the paper. Geometry of a space suggests a focus on the angles, sizes and dimensions of things.  When restricting to a discrete space, the geometry focuses on characterizing the structure of the space.  The focus of this paper is not on the underlying structure of this space or how it relates to other spaces, instead, it looks at computing distances and bounding the diameter of the underlying graph induced by the metric.  Choosing a title to match the strongest contributions of the paper would be helpful.
    - We have changed the title to "Discrete Coalescent Trees"

- p 2, l 10: Characterizing the BHV space of trees as modeling tree as "points in a cubical complex" is correct but uninformative to your narrative.  If you want to frame it in terms of complexes, explain the terms.
    - We simplified this by changing it to: "For example, trees in the BHV-space [1] are parametrised by their branch lengths."

- p 2, l 12: Justify the (correct) claim that BHV space is not suitable for coalescent trees.  As it reads now, it consists of several disjointed and not well-defined terms that weakens your claim.  Define or sketch what coalescent trees are before using and explain about the importance of timing on internal nodes and concisely explain why these previous models fail to capture this.

    - We modified this to: "One  important  example,  the  BHV-space  [2],  consists  of  orthants,  representing  tree topologies.  Trees are parametrised by their branch lengths.  This parameterisation is however not suitable for time trees because changing the times of an evolutionary event in the tree implies that all preceding events change their times as well.  Hence two trees can be close to each other in this space even though the timing of many internal nodes is different in the two trees.  Furthermore,subspaces of BHV-space associated with different ranked topologies have different volumes, which makes analysing distributions in this tree space difficult.  For a more detailed discussion on this we refer the reader to [10]. "

- p 2, l 20: As written, this suggests that none of the spaces mentioned in this paragraph have polynomial algorithms to compute distances. Is that really true? 
    - We have clarified that algorithms for BHV and tau-space are known: "For summary trees based on distance measures, this might result in losing such information shared between trees in the summary tree. Because of this, BHV- and tau-space are not suitable for most applications, even though shortest paths can be computed efficiently."

- p 6, l 14:  Provide a proof, not just intuition, that this is true.
    - We have added a proof

- p 6, l 25: The statement immediately following the proof that the theorem proves running time needs more justification. If the theorem holds, it does follow, but you need to say why.
    - We changed our wording here: "The worst-case running time of FindPath^+ on discrete coalescent trees is O(mn), which we will explain in detail in Section 4.3.". We would prefer to avoid going into too much detail here about the running time because this topic is closely related to the diameter discussion, which is done in Section 4.3.

- p 7, l 50:  Before the "It follows…", explain why the conclusion holds.
    - We have added to clarify: "Since R' is on the shortest paths FP(R,T) and FP(R,T'), the length of these paths is the sum of the length of the path up to R' plus the length of the remaining part of the path, respectively.
	It follows d(T,R) = d(R,T) = |FP(R,T)| = |FP(R,R')| + |FP(R',T)| = d(R,R') + d(R', T) and d(T',R) = d(R,T') = |FP(R,T')| = |FP(R,R')| + |FP(R',T')| =  d(R,R') + d(R', T')."

- p 11, l 11: The notation in the definition of M_T does not make sense.  What is the scope of the universal quantification?  What does the ":" mean?
    - We have updated the definitions of the two sets to clarify: "P(T,R) ={(a_i,a_j)|rank(a_i)_T<rank(a_j)_T and rank(a_i)_R>rank(a_j)_R}, M(T,R) ={a_i|for all l with rank(a_l)_T≤rank(a_i)_T it is rank(a_l)_R>rank(a_i)_R} ∩ {a_i|rank(a_i)_T<min{rank(a_1)_T,rank(a_2)_T}}". We also added a paragraph to explain these sets after the theorem: "The  set P(T,R)  in  Theorem  4  is  the  set  of  transpositions  for  the  caterpillar  trees T and R. M(T,R) contains the leaves a_i in T for which in the representation of T as a list (i) every leaf that is below a_i in T (if a_i is in the cherry, this includes the other cherry leaf) is above a_i in R and (ii) no cherry leaf of R is below a_i in T."

- p 11, l 27:  The proof is likely correct, but without a clear definition of M_T and m_T, it is impossible to verify.
    - We have updated the definition and added a small description, see the previous comment.

- p 13, l 42:  Replace "he" with "the".
    - Done


### Reviewer 3

#### MAJOR COMMENTS  (mostly related to proofs)

- p5 l54-55 and in the proof of Theorem 1: Can you please add some explanation on why potential NNI moves that involve the root of T_r and R_r don't cause any problem in translating a shortest path between T_r and R_r into a shortest path between T and R.
    - This has been solved by re-writing the proof of Theorem 1

-  proof of Theorem 1: This proof needs more detail. Starting with the statement of the theorem, I think what you want to show is that d(R,T)=FP(R_r,T_r). Once the statement of the theorem is clarified, I suggest you establish both inequalities separately; i.e. show that (i) given a shortest path between R_r and T_r that FindPath as described in [4] returns, construct a path between R and T of the same length and (ii) given a shortest path from R to T in DCT_m construct a path from R_r to T_r in RNNI of the same length. The current version of the paper has an informal justification of why Theorem 1 holds prior to the statement of Theorem 1 and -- in my opinion -- a handwaving argument in the proof of Theorem 1. Please revise to make the argument more precise and convincing (also take into account Comment (1) above). Lastly, please explain prior to Theorem 1 why no generality is lost by assuming that $m$ is the maximum root height of R and T. This is only said further down the page.
    - The proof of Theorem has been re-written, using this idea of splitting the proof into two cases. Thank you for this very helpful feedback. We also changed m to be greater or equal to the maximum root height of the given trees and extended the discussion on restricting m to the maximum root height later: "Note that we do not need the parameter m in practice, as the distance between any two trees in DCT_m' is the same as their distance in DCT_m for any m > m'. This follows from FindPath applied to extended ranked versions of trees T and R, where for m>m' all clusters induced by nodes with rank greater than m' are the same in T and R, meaning that they are preserved on FP(T_r,R_r). And since d(T,R) = |FP(T_r,R_r)| (Theorem 1), it follows that the distances between T and R are the same for all m > m'. Therefore, if the distance between two trees is to be computed, we can simply choose m to be the maximum root height of the given trees and compute their distance in DCT_m."

- Since the algorithm FindPath as described in [4] plays a crucial role, I suggest to give full details of the algorithm in the present paper. As FindPath in [4] is relatively short, I think it is best to include its pseudocode and a description of how the algorithm works. First, this may help convincing the reader that Algorithm 2 -- a generalisation of FindPath to DCT_m -- is indeed correct. Second, many proofs (e.g. proof of Theorems 2 and 3) in the present paper make substantial use of FindPath [4] and, so, it is important for the reader to understand how FindPath works in RNNI. When including information on how FindPath [4] works, please include the information that is needed to understand the proofs of Theorems 2 and 3.
    - We added a description of FindPath and the Pseudocode for RNNI (Second paragraph Section 3, Algorithm 1), and also a description for FindPath^+.

- p7 l58: I don't know why it is correct to conclude here that d(R,T)=d(R',T')-1. Please clarify.
    - we have added to clarify: "Therefore, T is the first tree following T' on FP(T',R'), resulting in |FP(T',R')| = |FP(T',T)| + |FP(T,R')| and hence d(T',R') = 1 + d(T,R'). With the observations d(T,R) = d(R,R') + d(R',T) and d(T',R) = d(R,R') + d(R',T') it follows d(T',R) = d(R,R') + d(R',T') = d(R,R') + d(T,R') + 1 = d(T,R) + 1. From the assumption that T' is the first tree on a shortest path from T to R we can however follow d(T',R) = d(T,R) - 1, which leads to a contradiction."

- Theorem 3: To show that the space of caterpillar trees is convex under RNNI, the proof of Theorem 3 makes use of R_r and T_r which are not caterpillars. Can you please explain why this is not causing any issue (a reference to Theorem 1 may help).
    - We have added a clarification: "Let T and R be two caterpillar trees in DCT_m. We prove the theorem by showing that there is a caterpillar tree T' that is a neighbour of T and closer to R than T. The existence of a shortest path consisting only of caterpillar trees between T and R follows inductively. In the proof of Theorem 1 we have seen that all paths in DCT_m can be transformed to paths in RNNI between the extended ranked versions of trees, and vice versa, such that these two paths are of equal length. It is therefore sufficient to show that all shortest paths between T_r and R_r, the extended ranked versions of T and R, consist only of trees T' such that T'_r^d is a caterpillar tree."

- p10: Consider the two trees R=(((1,2),3),4) and R=T=(((2,1),3),4). Then d(R,T)=0. However, depending on how exactly the triangle of the lollipop graph is constructed, you may need one swap. Please add more details on how the lollipop graph is constructed for two trees R and T that have the same cherry so that the issue can be resolved.
    - We have added: "On a_1 and a_2, which represent the cherry of the caterpillar tree, we place the tokens with goal vertices b_1 and b_2 so that if a_i = b_j for some i,j in {1,2}, the token with goal vertex b_j=a_i is placed on the node labelled a_i=b_j."

- p11 l33: Please clarify why establishing the given inequality proves equality.
    - We have changed the proof and now use an idea similar to the proof of Theorem 3.

- While Section 6 is interesting in the sense that it provides a connection between RNNI and partition lattices, the section lacks many details of which a few are listed next. Please revise the entire section.
(1) say what the set of edges in a partition lattice is; e.g. in Figure 10 why is there no edge between {1,2,3,4} and {1}{2}{3}{4} [after all, one is a refinement of the other]
(2) formalise when two neighbouring chains correspond to an NNI move and when to a rank move
(3) p17 l25-30: I understand how the mapping from a tree to a chain is done, but why it gives a bijection remains unclear.
    -  We have added a note how the figure is to be interpreted: "Note that in this figure there is only an edge between two partitions X and Y if uniting two sets of X results in Y. This implies that two partitions X <= Y are connected by a path consisting of single edge only if |X| = |Y| + 1"
    - The proof of Theorem 8 has been re-written. It now goes into more detail on how the bijection between RNNI and the graph of maximum chains of the partition lattice is constructed. We also explain in this proof how NNI and rank moves correspond to changes in the maximum chains.

#### MINOR COMMENTS

- p1 l22: and geometry --> and the geometry
    - Done

- p1 l25 "computational formalisms": What is meant here? What is formalised?
    - To clarify, we changed this to "computational applications"

- p2 l8-9: What is meant by "the running tree". Yes, the reader may be able to guess, but it's better to be precise.
    - We changed this to "[...] to propose trees that are are measurably similar to a given tree in tree search algorithms."

- p2 l19: Explain why it is problematic if a shortest path between two trees contains the star tree.
    - To clarify, we changed this to: "[...]. This can be problematic in applications, when for example a pair of trees share some evolutionary information in form of a subtree, but this information is not preserved on a shortest path between them.
    For summary trees based on distance measures, this might result in losing such information shared between trees in the summary tree."

- p2 l28: Say what $m$ is.
    - To clarify, we changed this to :"In this paper we introduce the space DCT_m of discrete coalescent trees, where internal nodes are assigned unique discrete times, and the time of the root is bounded from above by the integer $m$."

- p2 l34: generalise --> generalised
    - Done

- p2 l40-42: the connection between RNNI and partition lattices is not part of Section 5 but part of the Appendix. Please revise.
    - We updates this to: "We finish this paper with a conclusion and propose directions for further research (Section 5). In the supplement we provide a connection between the RNNI space and partition lattices."

- p2 l59: we say rank of --> we say the rank of
    - Done

- p3 l18: referred to as (a_5)_T, ({a_1,a_5})_T --> referred to as (a_5)_T or ({a_1,a_5})_T
    - Done

- p3 l40: every internal nodes --> every internal node
    - Done

- p3 l42: The current definition of the vertex set of DCT_m is missing that all trees have a fixed number of leaves. It is mentioned further down the page, so either move it up or include it in the definition of the vertex set of DCT_m.
    - We added a comment on the number of leaves: "The vertex set of DCT_m is the set of trees on $n$ leaves with root time less or equal to $m$. Note that we assume the number of leaves $n$ of the trees in the graph DCT_m to be fixed throughout this paper."

- p3 l48: Please explain what you mean by "both of length one". For example say something like "an edge (u,v) has length one if time(u)-time(v)=1
    - We added the definition for the length of an edge: "The length of an edge (u,v) in a discrete coalescent tree is the time difference of the nodes bounding the edge: time(u) - time(v)."

- p3 l49: shrinking e and f to nodes --> contracting e and f
    - We changed this

- p3 l49: Be more careful with "identical trees" here. On page 2, a tree is defined to be a rooted binary discrete coalescent tree. However, after contracting an edge, the resulting graph is non-binary. To get around the non-binary issue, an NNI move could be defined as an operation on T to obtain R. The current (equivalent) definition changes R and T and then checks if the two resulting trees are identical.
    - In the definition of "identical" trees we state that we do not require the trees to be binary: "We furthermore call two trees (not necessarily binary) identical if there is a graph isomorphism between them preserving leaf labels and times."

- p4 l29: three possible moves --> three possible types of moves
    - We changed this

- p5 l13 (i.e. line 7 of the pseudocode): Delete indentation.
    - We deleted the indent

- p5 l58: And explanation of what it means to "preserve clusters" (what you mean is common clusters) is only given at the beginning of Section 4. Consider to reorganize the material. As a reader, I find it frustrating having to guess what is meant and then find out a page later.
    - We added a definition of this ("For two trees T and R and a cluster C that is present in both T and R, we say that a path p from T to R preserves C if every tree on p contains C.") as well as a lemma (Lemma 1) showing that for ranked trees T and R sharing a cluster C all trees on FP(T,R) also contain this cluster

- p6 l4: FP() is not defined. Throughout the paper it would be good to distinguish between FP() as the result of the FindPath algorithm presented in [4] and FP'() as the result of the FindPath algorithm (i.e. Algorithm 2) presented in the present paper.
    - We added the definition for FP :"We denote the path that FindPath computes for two tees T_r and R_r by FP(T_r,R_r).". We also renamed Algorithm 2 (now Algorithm 3 as we added pseudo-code for the version of FindPath for RNNI) to FindPath^+ and refer to the corresponding path as FP^+(T,R) and made the use of FP and FP^+ consistent throughout the paper.

- p6 l5: "interpreting some rank moves" is vague. The rank moves that are interpreted as length moves are defined as "rank moves corresponding to length moves". The terminology can be used here to make the sentence precise.
    - We specified, which rank moves we mean: ", interpreting the rank moves corresponding to length moves between T_r and R_r as length moves."

- p6 l41: give the algorithm another name so that it can be distinguished from FindPath in [4]. Throughout the paper, it is sometimes unclear to which version you are referring (see also related comment on p6 l4).
    - We have renamed the algorithm for DCT to FindPath^+ and denote the corresponding path by fp^+(T,R).

- p6 l9: "centroid-based tree sample summary methods" comes a bit out of the blue.
    - We added a brief explanation: "This property is also desirable in centroid-based summary methods, where a summary tree minimises a function on distances to trees in the given tree set."

- p7 l16: Please make it explicit and say that no rank or length moves are allowed in NNI. In fact, I would define the NNI space earlier in Section 2 since it is used repeatedly throughout the paper.
    - We added this to our explanation of the NNI graph: "In the NNI graph, trees have no times and NNI moves are allowed on every edge, while rank moves and length moves are not possible as no times are assigned to internal nodes."

- p6 l6-13: There is related work on the cluster property that should be cited here in addition to [17]. The cluster property often comes up as the "cluster reduction" in the literature which may give a starting point for a literature search. At least the following two papers spring to mind, but there are likely others:
Baroni, M., Semple, C., & Steel, M. (2006). Hybrids in Real Time. Systematic Biology, 55(1), 46-56. [as an example of cluster preservation]
Bordewich, M., & Semple, C. (2004). On the computational complexity of the rooted subtree prune and regraft distance. Annals of Combinatorics, 8(4), 409-423. [as an example of another tree metric that 'almost' preserve clusters]
    - We highlighted the importance of the cluster property by mentioning the paper by Bordewich and Semple in the Cluster Property section: "Related  to  the  cluster  property  is  the  idea  to  split  the  computation  of  distances  into computing the distance between the subtrees induced by a shared cluster and the remaining tree[2].". We also emphasise the importance of preserved clusters for various applications in the introduction: "This includes in particular the cluster property, which a tree space has if all shortest paths between two trees sharing a cluster preserve this cluster.  A tree space with this property is desirable for constructing summary trees, as summaries for a set of trees sharing a cluster should also contain that cluster, a property that BHV-space and tau-space do not have, as summary trees often end up being start trees. Clusters have also shown to play an important role in the development of algorithms for computing distances between trees [3], as well as in constructing phylogenetic networks from trees [1]."

- p7 l27: I have read this sentence many times and still don't know what is meant here. I am guessing it can be reworded as follows: We furthermore assume that there is no tree pair R^* and T^* such that (i) d(R^*,T^*) < d(R,T) and (ii) there exists a shortest path p' between R^* and T^* that contains a tree that does not have all clusters that are shared by R^* and T^*.
    - We agree that this sentence is hard to understand. We changed this to: "We furthermore assume that there is no pair of trees T',R' with d(T',R') < d(T,R) that shares a cluster C' and is connected by a shortest path p' that does not preserve C'. We hence say that T and R give a minimum counterexample."

- p8 l13: it is be a shortest --> it is a shortest
    - We changed this

- p8 l22: is hence convex in RNNI --> is hence convex in RNNI and DCT_m
    - We changed this

- p8 l26: can be achieved in DCT_m --> can be achieved in DCT_m for pairs of caterpillars
    - We changed this

- p8 l35: be the leaf with parent with maximum --> be the leaf whose parent has maximum
    - We changed this

- p8 l36: among those whose --> among those leaves whose
    - We changed this

- p8 l42: $T_r^d'$ looks strange. Please reconsider the notation.
    - We agree that the notation might look a bit strange. We do however not want to simplify this notation, as we cannot think of a simpler way to denote these subtrees without loosing important information.

- p9 l57: What is meant by "analogous". What should be mentioned here is that an instance of computing d(R,T) where R and T are caterpillars can be translated into an instance of the Token Swapping Problem such that the number of swaps equals d(R,T).
    - We decided to clarify this: "A problem related to the shortest path problem for caterpillar trees in RNNI is the Token Swapping Problem [11] on a special class of graphs, so-called lollipop graphs.
    We will show that a pair of caterpillar trees in RNNI can be translated to an instance of the Token Swapping Problem, such that the RNNI distance between the trees is equal to the number of swaps, as explained in the following."

- p10 l9: by one edge --> by exactly one edge
    - We changed this

- p10 l10: that corresponding --> that corresponds
    - We changed this

- p10 l20: connecting complete graph and path --> connecting the complete graph with the path
    - We changed this

- p10 l22: such that the neighour --> such that the unique unlabeled neighbor
    - We changed this

- p11 l18-25: move the text prior to the statement of Theorem 4. Also "transpositions" (l18) should be italicised.
    - We have updated this paragraph and moved it to be the last paragraph before Theorem 4: "For improving on the time-complexity of computing distances between caterpillar trees, we use a representation of caterpillar trees as a list of leaves, ordered according to increasing rank of their parents. The caterpillar tree on the left of Figure 7 for example can be represented as (a_4,a_5,a_3,a_2,a_2) or (a_5,a_4,a_3,a_2,a_1). There are two possible list representations of a caterpillar tree because the first two leaves (a_4 and a_5 in this example) share their parent of rank one. For two given caterpillar trees T and R we call a pair of leaves (a_i,a_j) transposition, if the rank of the parent of a_i is lower than the rank of the parent of a_j in T, and the opposite is true for R: rank(a_i)_T < rank_T(a_j) and rank(a_i)_R > rank_R(a_j)."

- p13 l39: Does this mean that there can be more efficient algorithms that return the distance between two trees only as opposed to returning a shortest path (including all trees on the path) between two trees? Please clarify.
    - Yes. We clarified this: "There can however be more efficient algorithms for computing distances, if this is not done by computing the shortest path as FindPath does, but by finding an invariant that determines the distance without needing to compute every tree on a shortest path."

- p13 l41: as he minimum --> as the minimum
    - We changed this

- p14 l30-44: Can you say what the min/max distances are between trees in DCT_4? This may help to convince a reader that the radius of DCT_m is not necessarily equal to its diameter.
    - Yes. We added this: "The diameter of DCT_4 on three leaves is $(n-1)(n-2)/2 + (m-n+1)(n-1) = 5$, but there is no tree with this distance from the tree provided in Figure 11. The maximum distance between any tree in DCT_4 and the tree in Figure 11 is 4."

- p14 l51: Theorem 1 does not establish correctness of Algorithm 2. Please revise.
    - We updated our wording to: "We showed in Theorem 1 that FindPath can also be used to solve the shortest path problem in DCT_m.Therefore, it is required to transform discrete coalescent trees into ranked trees. With FindPath^+ we provided a modified version of the algorithm to avoid this conversion of trees."

- p15 l20-22: How is the transfer from DCT_m to t-space done and how can distances in t-space be approximated?
    - We added an explanation of how this is done: "Our results, however, provide a way to approximate distances between time-trees. Therefore, time-trees first need to be discretised to become discrete coalescent trees between which the DCT_m distance can be computed and used as approximation of the distance between time-trees in t-space."

- p15 l25: Since choice of m --> Since the choice of m
    - We changed this

- p16 l 60: I could not find open problems / ideas for future research in Section 6.
    - We deleted the corresponding sentence.

- p17 l12: Please check -- I think what you mean is a maximUM chain.
    - We have corrected this to maximum chain

- p17 l23-24: Can you give an example / more details on how FindPath can solve problems on lattices and which complexity results in the context of RNNI can be translated into complexity results for problems on lattices.
    - Yes. We added a few sentences to clarify this: "With the bijection between maximum chains in the partition lattice and ranked trees, as described in the proof of Theorem 8, FindPath can be used to find shortest paths in the graph of maximum chains of partition lattices as described in the theorem. Therefore, one just needs to translate the two input chains into ranked trees, run FindPath, and translate the path of ranked trees back into maximum chains in Pi_n. The problem of computing shortest paths in this graph can hence also be solved in O(n^2)."

- p17 l35: bold --> dashed
    - We updated this: "The four dashed chains correspond to the following RNNI path."


### REVIEWER 1

#### Specific comments

- The abstract does not reflect the contribution of the manuscript, I recommend re-writing it. I suggest removing the first two paragraphs of the abstract and expanding the third paragraph in a way that clearly states the contribution:  you define a space of DCT based on NNI, rank swaps and time-updates moves of labeled ranked tree shapes with internal labels in the set {1,…,m} and propose a distance between two trees as the geodesic distance on the space. Computation of the proposed distance is polynomial in m.
    - We shortened the first two paragraphs of the abstract and expanded the third paragraph: "Computational inference of dated evolutionary histories relies upon various hypotheses about RNA, DNA, and protein sequence mutation rates. Coalescent theory is a popular class of evolutionary models that implements the molecular clock hypothesis, under which times are inferred from mutation rates, to facilitate computational inference of dated phylogenies. Methodologically, phylogenetic inference methods require a tree space over which the inference is performed, and the geometry of this space plays an important role in statistical and computational aspects of tree inference algorithms. It has recently been shown that molecular clock, and hence coalescent, trees possess a unique geometry, different from that of classical phylogenetic tree spaces which do not model mutation rates.
    Here we introduce and study a space of discrete coalescent trees, that is, we assume that time is discrete, which is inevitable in many computational applications. This tree space is a generalisation of another known trees space, called the ranked nearest neighbour interchange space, and is built upon tree-rearrangement operations. Our advances in this paper do not only generalise existing results about ranked trees, including an algorithm for computing distances in polynomial time, but in particular provide new results for both the space of discrete coalescent tree and the space of ranked trees. We establish several geometrical properties of these spaces and show how these properties impact various algorithms used in phylogenetic analyses. Our tree space is a discretisation of a known time tree space, called t-space, and hence our results can be used to approximate solutions to various open problems in t-space."

- Page 2, Lines 7-8: A similarity measures for these trees…. I do not think this is true. We can propose trees that are far from each other in RNNI/DCT space but closer to each other in (posterior) probability space, for example with Metropolis-Hastings chains.
    - We do not think that we need to change this, because proposals are needed. If they are accepted or not is a different questions, which we do not discuss here.

- Page 2, Lines 17-18: It would be useful to briefly define t-space and tau-space.
    - We added brief descriptions of these tree spaces: "The t-space is a simplical complex, where each simplex corresponds to a ranked tree topology and trees are parametrised by the actual time assigned to internal nodes. The τ-space is made out of orthants that correspond to ranked tree topologies and time differences between consecutive nodes  are  used  as  parameterisation."

- Algorithm 2 is very hard to understand. Please add comments to the important lines of the algorithm. Line 1 has some new notation: . p:=[T_{1}] ?. What does it mean decreased by an RNNI move in line 6? Similarly, line 12.?
    - We agree that the pseudo-code is hard to understand. That is why we made quite a few changes in this section. We added an explanation and Pseudo-Code for FindPath on ranked trees, which will also help explaining the version for discrete coalescent trees. And we also describe the version of FindPath for discrete coalescent trees in words before we state the pseudo-code. Note that the version of FindPath modified for discrete coalescent trees is now called FindPath^+ to distinguish it from the algorithm on ranked trees. We also added a definition of the representation of paths as a list of trees: "We write a path in DCT_m as a list of trees [T_0, T_1, ..., T_k], such that T_i and T_{i+1} are neighbours in DCT_m, and denote the length k of such a path p by |p|."

- First paragraph of proof of theorem 2 is confusing. Can it be better stated?
    - We see that the proof of Theorem was hard to understand. We have updated the first paragraph: " We assume to the contrary that there are two ranked trees T and R sharing a cluster C and a shortest path p between these trees where C is not present in every tree.
	We furthermore assume that there is no pair of trees T',R' with d(T',R') < d(T,R) that shares a cluster C' and is connected by a shortest path p' that does not preserve C'. We hence say that T and R give a minimum counterexample. Because of this minimality assumption on the length of p, the first tree T' following T on p does not contain C. Since NNI moves only change one cluster, C is the only cluster changed in T' compared to T, and all nodes with rank below (C)_T induce the same clusters in T and T' (Figure 5). We now compare distances d(T,R) and d(T',R) by using properties of FindPath."

#### Small comments:

- Page 1, Line 47: Under a coalescent model, evolution…
    - We changed this
- Page 2, Line 34: change to “FindPath originally designed for RNNI space, can be generaliseD for the discrete coalescent trees space to compute shortest paths in polynomial time.
    - We updated this : "After introducing notations used throughout this paper (Section 2), we discuss how the algorithm FindPath[4], originally designed for trees in RNNI, can be generalised for the discrete coalescent tree space to compute shortest paths in polynomial time (Section 3)."

- Page 8, line 14 : It is be a shortest -> it is the shortest.
    - We changed this.
