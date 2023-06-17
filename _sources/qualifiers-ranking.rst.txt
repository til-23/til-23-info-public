Qualifiers - Leaderboard
~~~~~~~~~~~~~~~~~~~~~~~~

How will your team be evaluated in the qualifiers?
##################################################

There will be three different leaderboards shown **per tier** in the competition platform. Hence, there will be six different leaderboards, they are:

1. Novice - Object Detection & ReID
2. Novice - ASR 
3. Novice - Combined Result
4. Advanced - Object Detection & ReID
5. Advanced - ASR 
6. Advanced - Combined Result

We will be adopting an **equal scoring weightage** of 50% Object Detection & ReID combined, and 50% ASR for the consolidated rank on the "Combined Result" leaderboard (**based on rank position for both tasks, NOT the individual competition scores**). **Teams with both competitions submitted will be ranked higher in the "Combined Result" leaderboard than those who submitted either one.** If the consolidated rank is the same, then the individual competition scores will be calculated with this formula:

.. math::

   \frac{Overall\_CV\_Score + (100 - ASR\_Score)}{2}


To illustrate on how your team will be evaluated, one set of three example leaderboards are as shown below:

.. list-table:: Object Detection & ReID leaderboard (in order of ranking)
    :widths: 15 30 25
    :header-rows: 1

    * - Ranking
      - Team Name
      - mAP (%)
    * - 1
      - Team A
      - 72.803
    * - 2
      - Team B
      - 71.008
    * - 3
      - Team E
      - 68.563
    * - 4
      - Team C
      - 62.865
    * - 5
      - Team D
      - 57.865
    * - 6
      - Team G
      - 57.390
    * - 7
      - Team F
      - 57.365
    
.. list-table:: ASR leaderboard (in order of ranking)
    :widths: 20 50 50
    :header-rows: 1

    * - Ranking
      - Team Name
      - WER (%)
    * - 1
      - Team B
      - 7.852
    * - 2
      - Team A
      - 10.037
    * - 3
      - Team F
      - 11.272
    * - 4
      - Team D
      - 12.579
    * - 5
      - Team C
      - 15.215
    * - 6
      - Team G
      - 95.120
    
      

.. list-table:: Combined Result (in order of ranking)
    :widths: 15 30 30 30 30 30
    :header-rows: 1

    * - Ranking
      - Team Name
      - CV (%)
      - ASR (%)
      - Overall (%)
      - Consolidated Ranking
    * - 1
      - Team B
      - 71.008
      - 7.852
      - 81.578
      - 1.5
    * - 2
      - Team A
      - 72.803
      - 10.037
      - 81.383
      - 1.5
    * - 3
      - Team C
      - 62.865
      - 15.215
      - 73.825
      - 4.5
    * - 4
      - Team D
      - 57.865
      - 12.579
      - 72.643
      - 4.5
    * - 5
      - Team F
      - 57.365
      - 11.272
      - 73.046
      - 5.0
    * - 6
      - Team G
      - 57.390
      - 95.120
      - 31.135
      - 6.0
    * - 7
      - Team E
      - 68.563
      - \-
      - 34.282
      - \-

Explanation:    

Team A's consolidated ranking is (1+2)/2=1.5, and combined score is (72.803+(100-10.037))/2 = 81.383 

Team B's consolidated ranking is (1+2)/2=1.5, and combined score is (71.008+(100-7.852))/2 = 81.578

Hence, B ranks higher than A

Team C's consolidated ranking is (4+5)/2=4.5, and combined score is (62.865+(100-15.215))/2 = 73.825 

Team D's consolidated ranking is (5+4)/2=4.5, and combined score is (57.865+(100-12.579))/2 = 72.643

Hence, C ranks higher than D

Team F's consolidated ranking is (7+3)/2=5, and the combined score is (57.365+(100-11.272))/2 = 73.046

Although Team F combined score is higher than Team D, but the combined rank is lower

Hence Team D is rank higher than F

Although Team E ranks 3rd in the CV challenge, but Team E did not have a valid submission for the ASR challenge.

Hence Team E ranks the lowest in the combined result.

Although Team G combined score is lower than Team E, but Team G has valid submissions for both challenge whereas Team E only has one.

Hence Team G is rank higher than E

**The top 8 of each tier will advance to the finals based on the Combined Result**

 