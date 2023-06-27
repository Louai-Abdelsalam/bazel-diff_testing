# Testing bazel-diff

## Steps to test:
- Switch to the first of the 2 commits you wanna compare.
- Run `bazel run //:bazel-diff -- generate-hashes starting_hashes.json -w $(pwd) -b bazel`
- Switch to the second ofthe 2 commits you wanna compare.
- Run `bazel run //:bazel-diff -- generate-hashes final_hashes.json -w $(pwd) -b bazel`
- Run `bazel run //:bazel-diff -- get-impacted-targets -sh starting_hashes.json -fh final_hashes.json -o impacted_targets.txt`
- Run `bazel query 'attr(tags, "\[(?!manual)", kind(test, //...))' --output label > all_test_targets_without_manual_tag.txt`
- Run `comm -1 -2 <(sort all_test_targets_without_manual_tag.txt) <(sort ./bazel-bin/bazel-diff.runfiles/evertz/impacted_targets.txt)`

#### Note: file names can of course be changed.