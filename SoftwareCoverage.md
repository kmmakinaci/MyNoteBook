# Branch Coverage, Statement Coverage, MC/DC

In our daily activities, we often use static and dynamic code analysis to improve overall software product quality.
But we are not always sure what kind of coverage is used in the analysis. Also, our product or company processes may require different aspects of code coverage for different certification types and levels.

Let us discuss the common understanding and misconceptions about code coverage, test coverage, and code analysis.

## Definitions of Structural Coverage Levels

Structural coverage metrics measure which parts of the source code have been executed during testing. They are essential for ensuring the thoroughness of unit and integration tests. The most common metrics, in order of increasing rigor, are:

*   **Statement Coverage:** Measures whether each statement in the code has been executed at least once.
*   **Branch Coverage:** Measures whether each branch (e.g., from an `if` or `switch` statement) has been executed. This includes both the true and false branches of every decision.
*   **Modified Condition/Decision Coverage (MC/DC):** A more rigorous metric that requires showing that each condition in a decision can independently affect the outcome of that decision.

Achieving a higher level of coverage implies that the lower levels have also been met. For example, 100% MC/DC coverage implies 100% branch and statement coverage.

## Structural Coverage Recommendations in ISO 26262

The ISO 26262 standard for functional safety recommends different levels of structural coverage for software unit testing based on the Automotive Safety Integrity Level (ASIL):

*   **ASIL A:** Statement coverage is "highly recommended" (++).
*   **ASIL B:** Branch coverage is "highly recommended" (++).
*   **ASIL C:** Modified Condition/Decision Coverage (MC/DC) is "recommended" (+).
*   **ASIL D:** MC/DC is "highly recommended" (++).

## Requirement Relations
 Also, code coverage reports are needed with a connection to requirements.
 If there are no documented requirements, they need to be deduced from the functional model, as it has executable specifications.

 It has to be made sure that for all requirements that have to be implemented by a software unit, at least one test case must be defined.
 After the requirements are finalized, requirements-based testing is applied.

 | Method | ASIL A | ASIL B | ASIL C | ASIL D |
 |---|---|---|---|---|
 | 1a Requirements-based test | ++ | ++ | ++ | ++ |
 | 1b Interface test | ++ | ++ | ++ | ++ |
 | 1c Fault injection test | + | + | + | ++ |
 | 1d Back-to-back comparison test between model and code (if applicable) | + | + | ++ | ++ |

This testing is done to ensure that the software unit behaves in an expected manner at the occurrence of any error.

## Resource usage test

This test is performed to ensure that the unit being tested does not consume excessive CPU resources or memory. Resource usage testing is usually done on the target platform or a simulator. This test is strongly recommended only when the software product is targeting to be ASIL D compliant.