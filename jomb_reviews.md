## Response to review

This paper has been sent to three reviewers, who all submitted reviews in a timely matter, and all recommended "major revision".  Their comments are listed below. The authors should prepare a revised version of their paper that carefully addresses the points listed below (many are straightforward but several will require care)- and return a document that highlights in colour the changes made (along with a response to reviews that describes how each of the points below has been addressed).
The revised paper will be sent back to the reviewers for a further check.


### Reviewer 2
The manuscript extends the metric for comparing ranked phylogenetic trees to a more general framework which they call discrete coalescent trees.  Let n be the number of leaves in a tree and assume that each leaf has a unique label.  Ranked phylogenetic trees are leaf labeled trees with the additional constraint that internal nodes are labeled by the "time" at which the speciation occurred and the assumptions that the times for parents are greater than their children and the labels are restricted to 1,…,n-1.  The authors previously showed that the popular nearest neighbor interchange (NNI) metric can be adapted to these ranked trees and computed in polynomial time— an intriguing result given the computational hardness of traditional NNI.

This paper relaxes the allowed labels of internal nodes to be integers up to m, where m >= n and calls these discrete coalescent trees.  The paper shows that the extended version of NNI is well-defined and gives a clever encoding of the discrete coalescent trees into ranked trees with an increased leaf set.  The encoding is clever, but the proofs are missing key details.  From the included intuition, they seem likely to be correct.  As such, I would suggest a major revision to include proofs of the theorems and address the following points:

*  The title is misleading as to the contents of the paper.  Geometry of a space suggests a focus on the angles, sizes and dimensions of things.  When restricting to a discrete space, the geometry focuses on characterizing the structure of the space.  The focus of this paper is not on the underlying structure of this space or how it relates to other spaces, instead, it looks at computing distances and bounding the diameter of the underlying graph induced by the metric.  Choosing a title to match the strongest contributions of the paper would be helpful.

*  p 2, l 10:  Characterizing the BHV space of trees as modeling tree as "points in a cubical complex" is correct but uninformative to your narrative.  If you want to frame it in terms of complexes, explain the terms.

* p 2, l 12:   Justify the (correct) claim that BHV space is not suitable for coalescent trees.  As it reads now, it consists of several disjointed and not well-defined terms that weakens your claim.  Define or sketch what coalescent trees are before using and explain about the importance of timing on internal nodes and concisely explain why these previous models fail to capture this.

* p 2, l 20:  As written, this suggests that none of the spaces mentioned in this paragraph have polynomial algorithms to compute distances.  Is that really true? 

* p 6, l 14:  Provide a proof, not just intuition, that this is true.

* p 6, l 25:  The statement immediately following the proof that the theorem proves running time needs more justification.  If the theorem holds, it does follow, but you need to say why.

* p 7, l 50:  Before the "It follows…", explain why the conclusion holds.

* p 11, l 11:  The notation in the definition of M_T does not make sense.  What is the scope of the universal quantification?  What does the ":" mean?

* p 11, l 27:  The proof is likely correct, but without a clear definition of M_T and m_T, it is impossible to verify.

* p 13, l 42:  Replace "he" with "the".



### Reviewer 3
The present paper establishes new results on a tree space of dated rooted binary phylogenetic trees. This new space -- called discrete coalescent trees (DCT_m) -- generalises the ranked nearest neighbor interchange space (RNNI) to trees whose root has rank/time at least n-1 (instead of exactly n-1 for RNNI), where n is the number of leaves of the trees. Using a generalised version of the polynomial time algorithm FindPath, which was recently published by two authors of the present paper (see reference [4]) as well as a transformation of discrete coalescent trees to ranked trees (with root height exactly n-1) the authors show that computing the (NNI) distances between two trees in DCT_m is solvable in polynomial time. The distance is equal to the minimum number of NNI, rank, and length moves that are required to transform one tree into another. In addition to the distance result, the authors

- show that the spaces of discrete coalescent trees (under NNI) and RNNI preserve clusters; i.e.  if two trees R and T share a cluster (clade) C then any shortest path between R and T only contains trees that also have C
- show that the spaces of discrete coalescent trees (under NNI) and RNNI is convex for caterpillar trees, i.e. if R and T are caterpillars, then there always exists a shortest path between R and T that only contains caterpillars
- establish novel diameter and radius results for both spaces (i.e RNNI and DCT_m)

The structure of the paper is clear, the results are novel and interesting, and the figures are helpful. I enjoyed reading the sections that connect the questions considered in the present paper to other problems in unrelated areas of mathematics (e.g. the token swapping problem and partition lattices). However, the writing of the paper (in particular that of the proofs) can be improved. Some paragraphs are lacking details or are rather vague which leaves the reader having to guess what is meant. I give detailed lists of major and minor comments below. Major comments point out paragraphs in the proofs that are challenging to read and/or are not convincing in the present form. When revising, please keep in mind that the reader is most likely less familiar with the material than you are. What is obvious to you (because you have worked on it for some time) may not all be obvious to the reader. The list of minor comments mainly includes typos and minor oversights of which there
are quite a few. I have focused on the first ten pages in my comments. There are likely more in the second half of the paper. While they are straightforward to fix, it would be good if a revised version could be carefully checked before resubmission.



MAJOR COMMENTS  (mostly related to proofs)


(1) p5 l54-55 and in the proof of Theorem 1: Can you please add some explanation on why potential NNI moves that involve the root of T_r and R_r don't cause any problem in translating a shortest path between T_r and R_r into a shortest path between T and R.

(2) proof of Theorem 1: This proof needs more detail. Starting with the statement of the theorem, I think what you want to show is that d(R,T)=FP(R_r,T_r). Once the statement of the theorem is clarified, I suggest you establish both inequalities separately; i.e. show that (i) given a shortest path between R_r and T_r that FindPath as described in [4] returns, construct a path between R and T of the same length and (ii) given a shortest path from R to T in DCT_m construct a path from R_r to T_r in RNNI of the same length. The current version of the paper has an informal justification of why Theorem 1 holds prior to the statement of Theorem 1 and -- in my opinion -- a handwaving argument in the proof of Theorem 1. Please revise to make the argument more precise and convincing (also take into account Comment (1) above). Lastly, please explain prior to Theorem 1 why no generality is lost by assuming that $m$ is the maximum root height of R and T. This is only said further down
the page.

(3) Since the algorithm FindPath as described in [4] plays a crucial role, I suggest to give full details of the algorithm in the present paper. As FindPath in [4] is relatively short, I think it is best to include its pseudocode and a description of how the algorithm works. First, this may help convincing the reader that Algorithm 2 -- a generalisation of FindPath to DCT_m -- is indeed correct. Second, many proofs (e.g. proof of Theorems 2 and 3) in the present paper make substantial use of FindPath [4] and, so, it is important for the reader to understand how FindPath works in RNNI. When including information on how FindPath [4] works, please include the information that is needed to understand the proofs of Theorems 2 and 3.

(4) p7 l58: I don't know why it is correct to conclude here that d(R,T)=d(R',T')-1. Please clarify.

(5) Theorem 3: To show that the space of caterpillar trees is convex under RNNI, the proof of Theorem 3 makes use of R_r and T_r which are not caterpillars. Can you please explain why this is not causing any issue (a reference to Theorem 1 may help).

(6) p10: Consider the two trees R=(((1,2),3),4) and R=T=(((2,1),3),4). Then d(R,T)=0. However, depending on how exactly the triangle of the lollipop graph is constructed, you may need one swap. Please add more details on how the lollipop graph is constructed for two trees R and T that have the same cherry so that the issue can be resolved.

(7) p11 l33: Please clarify why establishing the given inequality proves equality.

(8) While Section 6 is interesting in the sense that it provides a connection between RNNI and partition lattices, the section lacks many details of which a few are listed next. Please revise the entire section.
- say what the set of edges in a partition lattice is; e.g. in Figure 10 why is there no edge between {1,2,3,4} and {1}{2}{3}{4} [after all, one is a refinement of the other]
- formalise when two neighbouring chains correspond to an NNI move and when to a rank move
- p17 l25-30: I understand how the mapping from a tree to a chain is done, but why it gives a bijection remains unclear.



MINOR COMMENTS


p1 l22: and geometry --> and the geometry

p1 l25 "computational formalisms": What is meant here? What is formalised?

p2 l8-9: What is meant by "the running tree". Yes, the reader may be able to guess, but it's better to be precise.

p2 l19: Explain why it is problematic if a shortest path between two trees contains the star tree.

p2 l28: Say what $m$ is.

p2 l34: generalise --> generalised

p2 l40-42: the connection between RNNI and partition lattices is not part of Section 5 but part of the Appendix. Please revise.

p2 l59: we say rank of --> we say the rank of

p3 l18: referred to as (a_5)_T, ({a_1,a_5})_T --> referred to as (a_5)_T or ({a_1,a_5})_T

p3 l40: every internal nodes --> every internal node

p3 l42: The current definition of the vertex set of DCT_m is missing that all trees have a fixed number of leaves. It is mentioned further down the page, so either move it up or include it in the definition of the vertex set of DCT_m.

p3 l48: Please explain what you mean by "both of length one". For example say something like "an edge (u,v) has length one if time(u)-time(v)=1

p3 l49: shrinking e and f to nodes --> contracting e and f

p3 l49: Be more careful with "identical trees" here. On page 2, a tree is defined to be a rooted binary discrete coalescent tree. However, after contracting an edge, the resulting graph is non-binary. To get around the non-binary issue, an NNI move could be defined as an operation on T to obtain R. The current (equivalent) definition changes R and T and then checks if the two resulting trees are identical.

p4 l29: three possible moves --> three possible types of moves

p5 l13 (i.e. line 7 of the pseudocode): Delete indentation.

p5 l58: And explanation of what it means to "preserve clusters" (what you mean is common clusters) is only given at the beginning of Section 4. Consider to reorganize the material. As a reader, I find it frustrating having to guess what is meant and then find out a page later.

p6 l4: FP() is not defined. Throughout the paper it would be good to distinguish between FP() as the result of the FindPath algorithm presented in [4] and FP'() as the result of the FindPath algorithm (i.e. Algorithm 2) presented in the present paper.

p6 l5: "interpreting some rank moves" is vague. The rank moves that are interpreted as length moves are defined as "rank moves corresponding to length moves". The terminology can be used here to make the sentence precise.

p6 l41: give the algorithm another name so that it can be distinguished from FindPath in [4]. Throughout the paper, it is sometimes unclear to which version you are referring (see also related comment on p6 l4).

p6 l9: "centroid-based tree sample summary methods" comes a bit out of the blue.

p7 l16: Please make it explicit and say that no rank or length moves are allowed in NNI. In fact, I would define the NNI space earlier in Section 2 since it is used repeatedly throughout the paper.

p6 l6-13: There is related work on the cluster property that should be cited here in addition to [17]. The cluster property often comes up as the "cluster reduction" in the literature which may give a starting point for a literature search. At least the following two papers spring to mind, but there are likely others:

Baroni, M., Semple, C., & Steel, M. (2006). Hybrids in Real Time. Systematic Biology, 55(1), 46-56. [as an example of cluster preservation]

Bordewich, M., & Semple, C. (2004). On the computational complexity of the rooted subtree prune and regraft distance. Annals of Combinatorics, 8(4), 409-423. [as an example of another tree metric that 'almost' preserve clusters]

p7 l27: I have read this sentence many times and still don't know what is meant here. I am guessing it can be reworded as follows: We furthermore assume that there is no tree pair R^* and T^* such that (i) d(R^*,T^*) < d(R,T) and (ii) there exists a shortest path p' between R^* and T^* that contains a tree that does not have all clusters that are shared by R^* and T^*.

p8 l13: it is be a shortest --> it is a shortest

p8 l22: is hence convex in RNNI --> is hence convex in RNNI and DCT_m

p8 l26: can be achieved in DCT_m --> can be achieved in DCT_m for pairs of caterpillars

p8 l35: be the leaf with parent with maximum --> be the leaf whose parent has maximum

p8 l36: among those whose --> among those leaves whose

p8 l42: $T_r^d'$ looks strange. Please reconsider the notation.

p9 l57: What is meant by "analogous". What should be mentioned here is that an instance of computing d(R,T) where R and T are caterpillars can be translated into an instance of the Token Swapping Problem such that the number of swaps equals d(R,T).

p10 l9: by one edge --> by exactly one edge

p10 l10: that corresponding --> that corresponds

p10 l20: connecting complete graph and path --> connecting the complete graph with the path

p10 l22: such that the neighour --> such that the unique unlabeled neighbor

p11 l18-25: move the text prior to the statement of Theorem 4. Also "transpositions" (l18) should be italicised.

p13 l39: Does this mean that there can be more efficient algorithms that return the distance between two trees only as opposed to returning a shortest path (including all trees on the path) between two trees? Please clarify.

p13 l41: as he minimum --> as the minimum

p14 l30-44: Can you say what the min/max distances are between trees in DCT_4? This may help to convince a reader that the radius of DCT_m is not necessarily equal to its diameter.

p14 l51: Theorem 1 does not establish correctness of Algorithm 2. Please revise.

p15 l20-22: How is the transfer from DCT_m to t-space done and how can distances in t-space be approximated?

p15 l25: Since choice of m --> Since the choice of m

p16 l 60: I could not find open problems / ideas for future research in Section 6.

p17 l12: Please check -- I think what you mean is a maximUM chain.

p17 l23-24: Can you give an example / more details on how FindPath can solve problems on lattices and which complexity results in the context of RNNI can be translated into complexity results for problems on lattices.

p17 l35: bold --> dashed



### REVIEWER 1

Review of JOMB-D-21-00016


" The geometry of the space of Discrete Coalescent Trees "
By Lena Collienne, Kieran Elmes, Mareike Fischer, David Bryant and Alex Gabryushkin

The authors introduce and analyze a space of discrete coalescent trees (DCT), a time-discrete version of t-space in which the elements of the space are coalescent trees with n leaves and internal node labels in the set {1,…,m}, m>= n-1. The graph of discrete coalescent trees with vertex set the set of time-discrete coalescent trees, is defined by one-step (1) NNI move, (2) rank swap (rank move) and (3) internal node re-label +-1 (length move). The authors show that it is possible to compute the shortest path between trees in this space in polynomial time and in such a way that the path preserves a desirable property called “cluster property”. This path construction allows to define a distance between two trees as the length of the shortest path between them on the graph.

This paper extends the definition of the space on ranked coalescent trees based on RNNI (moves 1 and 2) to DCT by incorporating an additional move (move 3). Surprisingly, the algorithm for computing the shortest path in DCT is the same algorithm for computing the shortest path in RNNI of m+2 leaves. The key insight is to augment the space of DCT by caterpillar trees of m-n+1 internal nodes. The manuscript is very interesting with important contributions and recommended for publication.


Specific Comments:

The abstract does not reflect the contribution of the manuscript, I recommend re-writing it. I suggest removing the first two paragraphs of the abstract and expanding the third paragraph in a way that clearly states the contribution:  you define a space of DCT based on NNI, rank swaps and time-updates moves of labeled ranked tree shapes with internal labels in the set {1,…,m} and propose a distance between two trees as the geodesic distance on the space. Computation of the proposed distance is polynomial in m.




Page 2, Lines 7-8: A similarity measures for these trees…. I do not think this is true. We can propose trees that are far from each other in RNNI/DCT space but closer to each other in (posterior) probability space, for example with Metropolis-Hastings chains.

Page 2, Lines 17-18: It would be useful to briefly define t-space and tau-space.

Algorithm 2 is very hard to understand. Please add comments to the important lines of the algorithm. Line 1 has some new notation: . p:=[T_{1}] ?. What does it mean decreased by an RNNI move in line 6? Similarly, line 12.?

First paragraph of proof of theorem 2 is confusing. Can it be better stated?

Small comments:

Page 1, Line 47: Under a coalescent model, evolution…
Page 2, Line 34: change to “FindPath originally designed for RNNI space, can be generaliseD for the discrete coalescen
This paper relaxes the allowed labels of internal nodes to be integers up to m, where m >= n and calls these discrete coalescent trees. The paper shows that the extended version of NNI is well-defined and gives a clever encoding of the discrete coalescent trees into ranked trees with an increased leaf set. The encoding is clever, but the proofs are missing key details. From the included intuition, they seem likely to be correct. As such, I would suggest a major revision to include proofs of the theorems and address the following points:
Page 8, line 14 : It is be a shortest -> it is the shortest.