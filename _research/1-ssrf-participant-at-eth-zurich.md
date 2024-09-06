---
title: "SSRF Participant @ ETH Zurich"
collection: research
description_left: "Research Intern"
description_right: "Jul 2023 - Aug 2023"
---

I was one of the students accepted in the [SSRF Program](https://inf.ethz.ch/studies/summer-research-fellowship/program-structure.html) in the summer of 2023. I worked in the Programming Methodology group under supervision of Dr. Peter Muller, and Dr. Marco Eilers.

### Purpose

My main task during this internship was to find a way to integrate [CBMC](https://www.cprover.org/cbmc/) into [Viper](https://www.pm.inf.ethz.ch/research/viper.html), as a bounded model checker. In many cases, fully verifying a program might not be efficient or even possible, so the main idea here was to use model checking as a remedy to this problem. First step was to find a way to model Viper language in C, and then to see if CBMC is the right tool. We modeled some of the features including `inhale`, `exhale`, `predicate`.

### Results

CBMC had one main [issue with universal quantifiers](https://github.com/diffblue/cbmc/issues/203), where it would simply ignore them in many cases, resulting in a false result. We needed quantifiers to model non-deterministic behaviors of the data types. It was suggested to bound this non-determinism but that would result in a false verification. So it was mandatory to model data types using FOL. This resulted in a conclusion that CBMC is not the right tool for modeling checking Viper.
