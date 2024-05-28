---
Authors: Chrysie
Date: 7/5/2024
Purpose: picking out our variables
Version: 1
Notes: making it make sense
editor_options: 
  markdown: 
    wrap: 72
---

# School Selection

"10 schools were selected to be broadly representative of South-East
England, with a predicted intake of around 2000 pupils in September
2012.

*Note: we are using only child and teacher ratings*

# Outcome Variable

#### ***Psychological adjustment***

-   SDQ: Strengths and Difficulties Questionnaire

    -   Child (1, 2, 3)

    -   Teacher (1, 2, 3)

-   SDQ Impact Section

    -   Child (1, 2, 3)

    -   Teacher (1, 2, 3)

# Dependent Variables

#### ***Personal characteristics***

-   Wentzel's Learning Goal Pursuit - learning motivation

    -   Child Wave 1: C1_AG1, C1_AG2, C1_AG3, C1_AG4
    -   Child Wave 2: C2_AG1, C2_AG2, C2_AG3, C2_AG4
    -   Child Wave 3: C3_AG1, C3_AG2, C3_AG3, C4_AG4

-   Demographics - Free School Meals

#### ***Attitudes to school***

-   SCQ: School Concerns Questionnaire

    -   Child (1, 2, 3)

-   CDPQ: Child Development Project Questionnaire - *school liking*

    -   Child (1, 3)

        *Note: if there is anything to cut this will probs be it*

-   CDPQ: Child Development Project Questionnaire - *trust and respect
    for teachers*

    -   Child (1, 2, 3)

#### ***Social factors***

-   LiCs: School-oriented version fo the Loneliness in Children scale

    -   Child (1, 2, 3)

#### ***Academic attainment***

-   KS2: English, Maths, Science

    -   Teacher (1)

-   KS3: English, Maths, Science

    -   Teacher (2)

# Dataframe column codes

**X** = ppt number

**ID** = ppt ID

#### [**SDQ**]{.underline}

-   Child Wave 1: C1_B1 to 25 - recode: 7, 11, 14, 21, 25

-   Child Wave 2: C2_B1 to 25 - recode: 7, 11, 14, 21, 25

-   Child Wave 3: C3_B1 to 25 - recode: 7, 11, 14, 21, 25

#### [**SDQ Impacts**]{.underline}

-   cut because data is only from parents and teachers, not the children
    themselves

#### [**Wentzel's**]{.underline}

-   Child Wave 1: C1_AG1 to 4

-   Child Wave 2: C2_AG1 to 4

-   Child Wave 3: C3_AG1 to 4

#### [**FSM**]{.underline}

-   "FSM"

#### [**SCQ: School Concerns Questionnaire**]{.underline}

-   Child Wave 1: C1_SConcern1 to 20

-   Child Wave 2: C2_SConcern1 to 20

-   Child Wave 3: C3_SConcern1 to 20

#### [**CDPQ: Child Development Project Questionnaire (school liking)**]{.underline}

-   Child Wave 1: N/A

-   Child Wave 2: C2_SL1 to 5 - recode 1, 4

-   Child Wave 3: C3_SL1 to 5 - recode 3, 5

#### [**CDPQ: Child Development Project Questionnaire (trust and respect for teachers)**]{.underline}

-   Child Wave 1: C1_LT1 to 10 - recode: 1,3,5,7,9,10

-   Child Wave 2: C2_LT1 to 10 - recode: 1,3,5,7,9,10

-   Child Wave 3: C3_LT1 to 10 - recode: 2,4,6,8

#### [**LiCs: School-oriented version fo the Loneliness in Children scale**]{.underline}

-   Child Wave 1: C1_L1 to 16 - recode: 1,3,5,7,10,15

-   Child Wave 2: C1_L1,2,6,7,11,14,15 - recode: 1,7,15

-   Child Wave 3: C1_L1,2,6,7,11,14,15 - recode: 1,7,15

#### [**KS2: English, Maths, Science**]{.underline}

-   "KS2MathstestNUM"

-   "KS2EnglishtestNUM"

-   "KS2EnglishTANUM"

-   "KS2EngComb"

#### [**KS3: English, Maths, Science**]{.underline}

-   "Y7EnglishNC"

-   "Y7MathsNC"

-   "Y7ScienceNC"

-   "Y7NC"

-   "Y7EnglishIMYC"

-   "Y7MathsIMYC"

-   "Y7ScienceIMYC"

-   "Y7IMYC"

-   "Eng7"

-   "Math7"

-   "Sci7"

# Text file of variable codes

[**SDQ**]{.underline}

\*\*Total Difficulties: Child Wave 1. COMPUTE C1_TotalDifficultiesIMP =
RND(MEAN.3(C1_EmotionalSymptomsIMP, C1_ConductProblemsIMP,
C1_HyperactivityIMP, C1_PeerProblemsIMP)\*4).

\*\*Total Difficulties: Child Wave 2. COMPUTE C2_TotalDifficultiesIMP =
RND(MEAN.3(C2_EmotionalSymptomsIMP, C2_ConductProblemsIMP,
C2_HyperactivityIMP, C2_PeerProblemsIMP)\*4). EXECUTE.

\*\*Total Difficulties: Child Wave 3. COMPUTE C3_TotalDifficultiesIMP =
RND(MEAN.3(C3_EmotionalSymptomsIMP, C3_ConductProblemsIMP,
C3_HyperactivityIMP, C3_PeerProblemsIMP)\*4).

[**SDQ Impacts**]{.underline}

\*\**Behaviour Impact: Parent Wave 1. RECODE P1_B28 P1_B29 P1_B30 P1_B31
P1_B32 (1=0) (2=0) (3=1) (4=2)*INTO P1_B28r P1_B29r P1_B30r P1_B31r
P1_B32r *VARIABLE LABELS P1_B28r ‘P1_B28 recoded’ P1_B29r ‘P1_B29
recoded’ P1_B30r ‘P1_B30 recoded’ P1_B31r ‘P1_B31* recoded’ P1_B32r
‘P1_B32 recoded’. EXECUTE. *use above as required. DO IF (P1_B26 = 0).
COMPUTE P1_BehaviourImpactContinuousIMP = 0. ELSE IF (P1_B26 = 1).
COMPUTE P1_BehaviourImpactContinuousIMP = RND(MEAN.3(P1_B28r, P1_B29r,
P1_B30r, P1_B31r, P1_B32r)*5). ELSE IF (P1_B26 = 2). COMPUTE
P1_BehaviourImpactContinuousIMP = RND(MEAN.3(P1_B28r, P1_B29r, P1_B30r,
P1_B31r, P1_B32r)*5). ELSE IF (P1_B26 = 3). COMPUTE
P1_BehaviourImpactContinuousIMP = RND(MEAN.3(P1_B28r, P1_B29r, P1_B30r,
P1_B31r, P1_B32r)*5). END IF. EXECUTE. RECODE
P1_BehaviourImpactContinuousIMP (0=0) (1=1) (2 thru 10 =2) INTO
P1_BehaviourImpactStatusIMP. VARIABLE LABELS P1_BehaviourImpactStatusIMP
0 ‘normal’ 1 ‘borderline 2 ‘abnormal’.

\*\**Behaviour Impact: Parent Wave 2.* RECODE *P2_B28 P2_B29 P2_B30
P2_B31 P2_B32* (1=0) (2=0) (3=1) (4=2) *INTO P2_B28r P2_B29r P2_B30r
P2_B31r P2_B32r* VARIABLE LABELS P2_B28r ‘P2_B28 recoded’ P2_B29r
‘P2_B29 recoded’ P2_B30r ‘P2_B30 recoded’ P2_B31r ‘P2_B31 *recoded’
P2_B32r ‘P2_B32 recoded’.* EXECUTE. *use above as required. DO IF
(P2_B26 = 0). COMPUTE P2_BehaviourImpactContinuousIMP = 0. ELSE IF
(P2_B26 = 1). COMPUTE P2_BehaviourImpactContinuousIMP =
RND(MEAN.3(P2_B28r, P2_B29r, P2_B30r, P2_B31r, P2_B32r)*5). ELSE IF
(P2_B26 = 2). COMPUTE P2_BehaviourImpactContinuousIMP =
RND(MEAN.3(P2_B28r, P2_B29r, P2_B30r, P2_B31r, P2_B32r)*5). ELSE IF
(P2_B26 = 3). COMPUTE P2_BehaviourImpactContinuousIMP =
RND(MEAN.3(P2_B28r, P2_B29r, P2_B30r, P2_B31r, P2_B32r)*5). END IF.
EXECUTE. RECODE P2_BehaviourImpactContinuousIMP (0=0) (1=1) (2 thru 10
=2) INTO P2_BehaviourImpactStatusIMP. VARIABLE LABELS
P2_BehaviourImpactStatusIMP 0 ‘normal’ 1 ‘borderline 2 ‘abnormal’.

[**Wentzel's**]{.underline}

Learning Goal Pursuit: Child Wave 1. – mean.3. COMPUTE
C1_LearningGoalPursuitIMP = RND(MEAN.3 (C1_AG1, C1_AG2, C1_AG3,
C1_AG4)\*4).

Learning Goal Pursuit: Child Wave 2. – mean.3. COMPUTE
C2_LearningGoalPursuitIMP = RND(MEAN.3 (C2_AG1, C2_AG2, C2_AG3,
C2_AG4)\*4).

Learning Goal Pursuit: Child Wave 3. COMPUTE C3_LearningGoalPursuitIMP =
RND(MEAN.3 (C3_AG1, C3_AG2, C3_AG3, C3_AG4)\*4).

[**FSM**]{.underline} "FSM"

[**SCQ**]{.underline}

School Concerns Questionnaire Child Wave 1. – total score.12. COMPUTE
C1_SchoolConcernsIMP = RND(MEAN.12(C1_SConcern1,
C1_SConcern2,C1_SConcern3, C1_SConcern4, C1_SConcern5, C1_SConcern6,
C1_SConcern7, C1_SConcern8, C1_SConcern9, C1_SConcern10, C1_SConcern11,
C1_SConcern12, C1_SConcern13, C1_SConcern14, C1_SConcern15,
C1_SConcern16, C1_SConcern17, C1_SConcern18, C1_SConcern19,
C1_SConcern20) \*20)

Child Wave 2. – total score.12. COMPUTE C2_SchoolConcernsIMP =
RND(MEAN.12(C2_SConcern1, C2_SConcern2,C2_SConcern3, C2_SConcern4,
C2_SConcern5, C2_SConcern6, C2_SConcern7, C2_SConcern8, C2_SConcern9,
C2_SConcern10, C2_SConcern11, C2_SConcern12, C2_SConcern13,
C2_SConcern14, C2_SConcern15, C2_SConcern16, C2_SConcern17,
C2_SConcern18, C2_SConcern19, C2_SConcern20) \*20)

Child Wave 3. COMPUTE C3_SchoolConcernsIMP = RND(MEAN.12(C3_SConcern1,
C3_SConcern2, C3_SConcern3, C3_SConcern4, C3_SConcern5, C3_SConcern6,
C3_SConcern7, C3_SConcern8, C3_SConcern9, C3_SConcern10, C3_SConcern11,
C3_SConcern12, C3_SConcern13, C3_SConcern14, C3_SConcern15,
C3_SConcern16, C3_SConcern17, C3_SConcern18, C3_SConcern19,
C3_SConcern20) \*20)

[**CDPQ: Child Development Project Questionnaire (school
liking)**]{.underline}

Child Wave 2. RECODE C2_SL1 C2_SL4 (1=4) (2=3) (3=2) (4=1) INTO C2_SL1r
C2_SL4r. VARIABLE LABELS C2_SL1r 'C2_SL1 recoded' C2_SL4r 'C2_SL4
recoded'. EXECUTE. *run above as required. COMPUTE C2_SchoolLikingIMP =
RND(MEAN.3 (C2_SL1r, C2_SL2, C2_SL3, C2_SL4r, C2_SL5)*5).

Child Wave 3. RECODE C3_SL2 C3_SL3 C3_SL5 (1=4) (2=3) (3=2) (4=1) INTO
C3_SL2r C3_SL3r C3_SL5r. VARIABLE LABELS C3_SL2r 'C3_SL2 recoded'
C3_SL3r 'C3_SL3 recoded' C3_SL5r 'C3_SL5 recoded'. EXECUTE. *run above
as required. COMPUTE C3_SchoolLikingIMP = RND(MEAN.3 (C3_SL1, C3_SL2r,
C3_SL3r, C3_SL4, C3_SL5r)*5).

[**CDPQ: Child Development Project Questionnaire (trust and respect for
teachers)**]{.underline}

Child Wave 1 – mean.6. *RECODE* C1_LT1 C1_LT3 C1_LT5 C1_LT7 C1_LT9
C1_LT10 *(1=4) (2=3) (3=2) (4=1)* INTO C1_LT1r C1_LT3r C1_LT5r C1_LT7r
C1_LT9r C1_LT10r. *VARIABLE LABELS C1_LT1r 'C1_LT1 recoded' C1_LT3r
'C1_LT3 recoded' C1_LT5r 'C1_LT5 recoded' C1_LT7r 'C1_LT7 recoded'
C1_LT9r 'C1_LT9 recoded' C1_LT10r 'C1_LT10 recoded'.* EXECUTE. *use
above as required. COMPUTE C1_LikingTeachersIMP = RND(MEAN.6 (C1_LT1r,
C1_LT2, C1_LT3r, C1_LT4, C1_LT5r, C1_LT6, C1_LT7r, C1_LT8, C1_LT9r,
C1_LT10r)*10).

Child Wave 2. *RECODE* C2_LT1 C2_LT3 C2_LT5 C2_LT7 C2_LT9 C2_LT10 *(1=4)
(2=3) (3=2) (4=1)* INTO C2_LT1r C2_LT3r C2_LT5r C2_LT7r C2_LT9r
C2_LT10r. *VARIABLE LABELS C2_LT1r 'C2_LT1 recoded' C2_LT3r 'C2_LT3
recoded' C2_LT5r 'C2_LT5 recoded' C2_LT7r 'C2_LT7 recoded' C2_LT9r
'C2_LT9 recoded' C2_LT10r 'C2_LT10 recoded'.* EXECUTE. *use above as
required. COMPUTE C2_LikingTeachersIMP = RND(MEAN.6 (C2_LT1r, C2_LT2,
C2_LT3r, C2_LT4, C2_LT5r, C2_LT6, C2_LT7r, C2_LT8, C2_LT9r,
C2_LT10r)*10).

Child Wave 3. *RECODE* C3_LT2 C3_LT4 C3_LT6 C3_LT8 *(1=4) (2=3) (3=2)
(4=1)* INTO C3_LT2r C3_LT4r C3_LT6r C3_LT8r. *VARIABLE LABELS C3_LT2r
'C3_LT2 recoded' C3_LT4r 'C2_LT4 recoded' C3_LT6r 'C2_LT6 recoded'
C3_LT8r 'C3_LT8 recoded'.* EXECUTE. *use above as required. COMPUTE
C3_LikingTeachersIMP = RND(MEAN.6 (C3_LT1, C3_LT2r, C3_LT3, C3_LT4r,
C3_LT5, C3_LT6r, C3_LT7, C3_LT8r, C3_LT9, C3_LT10)*10).

[**LiCs: School-oriented version fo the Loneliness in Children
scale**]{.underline}

Child Wave 1. – total score.10. RECODE C1_L1 C1_L3 C1_L5 C1_L7 C1_L10
C1_L15 (1=5) (2=4) (3=3) (4=2) (5=1) INTO C1_L1r C1_L3r C1_L5r C1_L7r
C1_L10r C1_L15r. VARIABLE LABELS C1_L1r ‘C1_L1 recoded’ C1_L3r ‘C3_L1
recoded’ C1_L5r ‘C1_L5 recoded’ C1_L7r ‘C1_L7 recoded’ C1_L10r ‘C1_L10
recoded’ C1_L15r ‘C1_L15 recoded’. EXECUTE. *run above as required*
**w1-all variables. COMPUTE C1_LonelinessIMP = RND (MEAN.10 (C1_L1r,
C1_L2, C1_L3r, C1_L4, C1_L5r, C1_L6, C1_L7r, C1_L8, C1_L9, C1_L10r,
C1_L11, C1_L12, C1_L13, C1_L14, C1_L15r, C1_L16)*16). EXECUTE.*** w1-to
match w2. COMPUTE C1_LonelinessIMP =RND(MEAN.5 (C1_L1r, C1_L2, C1_L6,
C1_L7r, C1_L11, C1_L14, C1_L15r)\*7).

Child Wave 2. *RECODE* C2_L1 C2_L7 C2_L15 *(1=5) (2=4) (3=3) (4=2)
(5=1)* INTO C2_L1r C2_L7r C2_L15r. *VARIABLE LABELS C2_L1r 'C2_L1
recoded' C2_L7r 'C2_L7 recoded' C2_L15r 'C2_L15 recoded'.* EXECUTE. *run
above as required. COMPUTE C2_LonelinessIMP = RND(MEAN.5 (C2_L1r, C2_L2,
C2_L6, C2_L7r, C2_L11, C2_L14, C2_L15r)*7).

Child Wave 3. RECODE C3_L1 C3_L7 C3_L15 (1=5) (2=4) (3=3) (4=2) (5=1)
INTO C3_L1r C3_L7r C3_L15r. *VARIABLE LABELS C3_L1r 'C3_L1 recoded'
C3_L7r 'C3_L7 recoded' C3_L15r 'C3_L15 recoded'. EXECUTE.* run above as
required. COMPUTE C3_LonelinessIMP = RND(MEAN.5(C3_L1r, C3_L2, C3_L6,
C3_L7r, C3_L11, C3_L14, C3_L15r)\*7).

[**KS2: English, Maths, Science**]{.underline}

"KS2MathstestNUM"

"KS2EnglishtestNUM"

"KS2EnglishTANUM"

"KS2EngComb"

[**KS3: English, Maths, Science**]{.underline}

"Y7EnglishNC"\
"Y7MathsNC"\
"Y7ScienceNC"\
"Y7NC"\
"Y7EnglishIMYC"\
"Y7MathsIMYC"\
"Y7ScienceIMYC"\
"Y7IMYC"\
"Eng7"\
"Math7"\
"Sci7"
