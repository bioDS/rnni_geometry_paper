Dear Prof Lewis,

we would like to thank you and the referees for reading our manuscript and providing further useful comments to improve it.
We have carefully gone through the comments and addressed them in the revised submission. We provide a point-by-point response below.
Please note that we introduced some further minor changes to the paper, which we mention after our response to the reviewers' comments.


### Reviewer 2

- The narrative and proofs of the manuscript are much improved.  However, I would suggest omitting the appendix or a revising with careful attention to the language since the conflating of the sets with the elements of them and terminology throughout the proof is confusing (e.g. uniting two sets of X_i does not result in X_{i+1} but an element of X_{i+1} and unclear how a set "receives" another set).
    - We decided to omit the appendix.


### Reviewer 3

- p5 l52: FP(T,R) is undefined
    - We added the definition of FP(T,R) to the paragraph explaining FindPath: "The algorithm FindPath (Algorithm 1) constructs a path between two ranked trees T and R in RNNI, which we denote by FP(T,R)."

- p6 l48: becomes parent --> becomes the parent
    - Done

- p7 l53: d_{DCT}(.) is undefined and never used again. Instead of using d() and having the reader guess which distance is meant, I suggest to use d_{DCT}(.) and d_{RNNI}(.) throughout. This would also be in line with other distances between pairs of trees.
    - We added indices DCT and RNNI throughout the manuscript.

- p7 l60: d(.) please clarify which distance is meant here
    - We added indices RNNI and DCT to the distance notations

- p9 l34: "identical to the restricting" is not correct. Replace with something like "identical to the restriction of all trees on".
    - We modified this sentence to: "We will see that this path is identical to the path resulting from restricting all trees on the path FP(T_r,R_r), [...]"

- p10 l22: "by one (length move): Are the parentheses necessary?
    - No. We deleted the parentheses.
  
- p10 l50: computing distances in NNI --> computing the NNI distance between two trees; also remove boldface in the same line
    - Done.

- p15 l8: a_3,a2,a_2 --> a_3,a_2,a_1
    - Done.

- p15: I suggest to move the paragraph between the statement of Theorem 4 and the proof of Theorem 4 up, so that p(T,R) and m(T,R) are defined before the statement of the theorem. Also, an example for the definition of p(T,R) would not go amiss.
    - The sets m(T,R) and p(T,R) are defined in the theorem, and the paragraph following the theorem can be seen as an alternative definition or interpretation of the definition in the theorem. We added an example for the sets P(T,R) and M(T,R): "The caterpillar trees T and R in Figure 7 for example have P(T,R) = {(a_1,a_3),(a_1,a_4),(a_1,a_5),(a_2,a_3),(a_2,a_4),(a_2,a_5),(a_3,a_4),(a_3,a_5)} and M(T,R) = {a_3,a_4}."

- p19 caption off Figure 11: Delete "(diameter)". It looks as if it is part of the formula.
    - We changed the caption to: "Tree in DCT_4 on three leaves for which there is no tree at the diameter distance 5 =(n−1)(n−2)/2+ (m−n+1)(n−1) from it."

The following comments did not need to be addressed as we decided to omit the appendix as suggested by reviewer 1.

- p22 l10: one-to-one relation --> bijection

- p22 l16: X_{n-2} --> X_{n-1}

- p22 l17: i=0,...,n-3 --> i=0,...,n-2

- p22 l27: maximal chain --> maximum chain


## Further changes
- We updated the proof of Theorem 2 to add a more detailed explanation why the cluster C is induced by the node with rank i in R.
- A few minor wording changes as per the diff file
