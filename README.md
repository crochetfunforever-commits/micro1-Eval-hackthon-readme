VigiCausality-Evaluation/
├── app/                      # Track A: drop VigiCausality here (adapter + contract; no app code shipped)
│   ├── adapter.py            #   loads app/vigicausality.py -> assess_case(case) -> dict
│   └── README.md
├── evaluation/
│   ├── schema.py             # standard response schema (pydantic) + JSON extraction
│   ├── scoring_engine.py     # 100-point scoring and critical-error detection
│   ├── metrics.py            # accuracy, macro P/R/F1, confusion matrix, kappa, weighted agreement
│   ├── evaluator.py          # scores outputs vs references, aggregates, finds weaknesses
│   ├── clinical_validation.py# validates the benchmark itself (structure, leakage, WHO-UMC consistency)
│   ├── consistency_tests.py  # repeat-run determinism check
│   ├── report_generator.py   # JSON / CSV / HTML reports
│   ├── tracks.py             # Track A and Track B execution
│   └── providers/            # model-independent interface, demo baselines, OpenAI-compatible and Anthropic clients
├── data/
│   ├── benchmark_cases.json|csv     # case inputs only (no answers)
│   ├── reference_answers.json|csv   # reference answers, kept separate from inputs
│   ├── recorded_outputs/            # outputs supplied from VigiCausality (4 cases)
│   └── source/supplied_cases_raw.json # the 4 supplied cases as received
├── tasks/tasks.json          # 10 evaluation tasks with rubric, difficulty and critical-error definitions
├── schema/assessment_output.schema.json
├── scripts/                  # benchmark authoring script, recorded-output mapper, CI import check
├── tests/                    # 70 automated tests
├── docs/                     # source selection report, technical validation report
├── .github/workflows/evaluation.yml
├── run_evaluation.py
├── requirements.txt          # pydantic, pytest
├── LICENSE  .gitignore  results/
