keep the naive reward for all these plots, and maybe try out different rewards and replicate the plots and see what changed

- [x] plot the certainty equivavelnt on the mean reward plot and see it coming up
- [x] plot the certainty equivavelt on another plot like mean reward
- [ ] plot the T horizon changing do it for different trained models (mean reward, certainty equivavelnt)
	one training cycle for each T
	(could even do one training cycle and do a snapshot at each target T)
	(the time horizon could even be a training variable)
- [x] plot the reward of the optimal strategy on the above three plots (red dots parallel with x axis)

It would be nice to see the agents trading strategy while its evolving. Put everything in info and recreate the rollouts to plot them.

- [x] make plots 16:9 and split them into two, color code baselines
- [x] run the evaluation for eval_num = 5000
- [ ] make a mermaid diagram of the training logic
