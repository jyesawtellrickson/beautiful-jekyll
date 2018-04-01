While the Tokyo metro is a marvel, [summary], there is always room for improvement. Many times I have seen the problem of some carriages having more space than others (usually the extremities), yet people still pile into the middle carriages. If people knew the occupancy of the different cars, they could adjust where they board to have more space. Not everyone will change, some want the fastest route out, or are just plain lazy, but there are people who would choose a bit more breathing space over the pack of sardines one is normally subjected to during rush hour.

So how could they achive this? Many trains come equipped with cameras to monitor security in the train. These cameras can be repurposed with video processing to work out real-time availabilities. For a sparsely populated carriage this is relatively easy, with people being simple outlines. For a packed carriage or anything with medium popularity, it becomes more difficult as we can no longer see people. In such a case, the best method will be to count heads via object recognition. A person's head should still be identifiable as a round object floating in the sky. Similarly, depending on the train type we could identify hands holding bars or rails.

In general, it would be sensible to set some thresholds for number of hands/heads and then we can define a few different groups off this, e.g. empty, some, many, packed. With different colours to indicate where to board (green, yellow, red, black).

An alternative is to use the same method and go ahead and label the set and train a neural network off this.

A further alternative could be what we don't see. The number of blocked features. Or number of human heads vs. human bodies.


The neat thing about trains is that you can't get on or off for around 2 minutes between each stop, you're crammed in there. So this means that we have 2 minutes to calculate the results and return to the user with enough time for them to decide where to stand.

## Thoughts
Actually we could calculate for previous stations, but at some major stations it can change drastically. Maybe we could use the average for previous days. Sadly this will probably change significantly, especially as people interact with the system more.
What about seats?
