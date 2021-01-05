# How it works... in short

Since you already know how to create the account and sign up, for sure, you anticipate learning how our Platform works. 

First, check out the diagram, depicting its general logic. 

![BL](https://github.com/mirpl/mvp-ta-knowledge-base/blob/master/assets/images/BasicFlow2.jpg?raw=true)

Looks simple, right? In case you not entirely understand how this flow goes, read the short step-by-step description:

1. Notice that the User undertakes some actions, while the Platform executes other ones. Nevertheless, no matter what is happening, you will see the results displayed in the respective pages. 
2. The crucial thing for smooth functioning and cooperating with the Platform is appropriately preparing the [repositories](docs/Using-the-Platform/Settings/Repositories.md). Without it, don’t even bother with starting your journey.
3. Once repositories are ready and you are signed up, you can create the first [Tests](../Using-the-Platform/Tests/Test-create-and-edit.md) using the scripts you fixed and chose. Add some Local Arguments, too, if you wish.
4. Push the code to GitLab or GitHub and commit it. 
5. If you see the commits, displayed in the Test details, you can use the Test to build a new [Test Plan](../Using-the-Platform/Test-Plan/Test-Plan-create-and-edit.md).
6. Neatly built Test Plans are the base for the [Jobs](../Using-the-Platform/Jobs/Jobs-create-and-edit.md) - the execution of your tests. The Platform will lead you effortlessly through the path of creating every Job you need. You will choose the branch and commit, and decide the set of arguments or the [schedule](../Using-the-Platform/Schedule/Schedules-and-Triggers.md) of Job execution. 
7. The most satisfying part of working with PowerFarm is… when you do nothing but waiting for the results. The trick is all the tests are being executed without even noticing it. You just read the status, but...
8. The Job being executed doesn’t always mean your role has ended here. The Triggers that are not finished yet can be paused, resumed, or deleted. 