# memory-leaks

## Example 1
The Load button will create 10,000 DIVs, each will be added to a global array called ```divList```, and inserted into the page.
You will see the DOM Nodes graph go higher after pressing Load, and not going back down after clicking Unload.
The Unload button will remove the DIVs from the page, but leave them in the ```divList``` array.
Taking Snapshots, or the Allocation instrumentation on timeline will allow you to drill down into these detached HTMLDivElements and see that divList is what holds them in memory.

## Example 2
The Load button will create 77 DIVs, inserting the first into the page, and every subsequent one into the previous DIV. The last DIV will also be referenced inside a function assigned to the global variable ```log```.
The Unload button will remove the DIVs from the page, but leave the ```log``` variable.
Taking a Snapshot will allow you to see how the last DIV is held in a function context, which is holding all the other DIVs in memory.

## Example 3
This is a great little ToDo app from [Ivan Radev](https://gist.github.com/ipradev/180be1facfffcd26e476fbcececa7eed) that has a memory leak. Perfect for practising what you have learnt, see if you can diagnose and fix the problem.
[The answer is here](https://gist.github.com/ipradev/b260ff0850de0800a5876805ec2c70e8)

## Slides
These will be released internally next week. I will announce the link in the ```#front-end-guild``` channel on Slack.