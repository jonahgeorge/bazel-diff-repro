# Repro

```
bazel run //:bazel-diff -- \
  --workspacePath . --bazelPath $(which bazel) generate-hashes /dev/stdout
```
