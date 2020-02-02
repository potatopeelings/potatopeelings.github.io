---
layout: post
title: AWS CloudWatch Events Rules and DST
tags: [ aws ]
---

AWS CloudWatch Events Rules use the UTC time zone. If we need a rule to trigger at a some local DST time, we must update the schedule expressions twice a year. Manually updating the schedule expressions is time consuming and error prone.

We can make this a bit easier by having 2 sets of rules, one set is enabled when there is DST and the other when there is no DST.

* my-five-o-clock-rule-enable-for-dst
* my-five-o-clock-rule-enable-for-no-dst

The update process is now a bit simpler and less error prone - search for `-for-dst` or `-for-no-dst` and enable or disable each set. We could also do this through the CLI or an AWS Lambda - enable the set that ends with one suffix and disable the other set.

### AWS CloudFormation

If our stack is set up by CloudFormation scripts, we include both rules in our cloudformation script and pick up the State from a bupotato.peelings@gmail.comild variable. The DST switch then becomes 2 steps

1. Run the lambda to toggle between the `-dst` and `-no-dst` sets.
2. Change the build variable so that new deployments enable the right set.
