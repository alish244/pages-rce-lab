---
title: test
date: 2026-01-01
# Testing YAML anchors and aliases for deserialization
a: &anchor value
b: *anchor
# Testing YAML merge keys
base: &base
  cmd: id
merged:
  <<: *base
  extra: test
# Ruby-specific YAML tags (would execute in Psych without safe loading)
# !ruby/object:Kernel
# !ruby/sym :system
exploit_attempt: !ruby/string:String "id"
---
# YAML Injection Test 31754
Content here.
