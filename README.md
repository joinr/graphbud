# graphbud
a horrific way to shovel graphs between xgml tooling (like yed) and powerpoint diagrams...


==Intro==
This hackjob arose from a colleague's need to iterate on diagrams in powerpoint (the Coin of the Realm for him), but 
with the lack of desire to layout node-by-node, connector-by-connector.

I remembered that there are excellent graph layout tools like graphviz and my favorite yEd, which would be perfect for 
the task.  

The only problem was the lack of decent interop between yEd and powerpoint.  You can copy and paste (eventually) .emf 
formatted graphics, but the result is not connected and thus not reactive in powerpoint.  You only get line fragments instead
of actual connected edges, which was a non-starter in this case.

THe current solution is a set of vba classes that connected diagrams (graphs) in powerpoint to xgml, and likewise read (and draw) xgml 
graph files as powerpoint diagrams (with connectors).

A typical workflow would be to have the graph creator build a poorly-laid-out skeleton (with connectors) in powerpoint
or even yEd, and then save the graph to xgml.  From here, we can use any layout tool to modify the xgml graph, and then 
draw it to a powerpoint slide.  The api is currently crap, and the drawing is limited to boxes and either linear or elbow connectors.

At best, this is a quickish way to get a manipulable layout of graph information into powerpoint for screwing around with.
