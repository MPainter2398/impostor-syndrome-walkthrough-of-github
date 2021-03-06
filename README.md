# Impostor Syndrome Walkthrough of GitHub
Talk from [Kansas City Developer Conference 2017](http://www.kcdc.info/sessions)

#### Abstract
As a long time Windows user and .NET developer, I’ve challenged myself to level-up my skills using Git and GitHub. As an industry, I feel we provide great content for beginners and for experts, but how do we target content for people in the intermediate category? To answer this question, I'm going to blog every. single. day. in 2017 about something new I’ve learned about using Git and GitHub. I’m hoping that showing my day by day progression can help others who are in similar situations, i.e. trying to reskill after years of industry experience.

I've been calling this guide "a penultimate guide" because I don't know what I don't know yet. I don't know which tips will be the best ones for an ultimate guide to Git(Hub). However, by the time KCDC rolls around, I will be more than half way through the Git(Hub) Tip of the Day series. This means I'll be half-way to an ultimate guide for intermediates leveling-up their skills to more advanced topics. This talk will cover the best of the best tips for this half-way point.

## Intro

So, um, about that blog every. single. day. idea... 

I made it until May 8th or **35% of my goal.** I left GitHub (the company) in early May for a true summer vacation. Having said that, I still found the challenge of writing all this content very rewarding. Forcing myself to blog about what I did **not** know forced me to learn or ask for help.  

If I could go back in time, this is the readme file I'd give myself. It contains the major lightbulb moments where Git(Hub) concepts click. Hopefully you'll (or somebody you know) will find it useful.

P.S. This is a git pun-free zone.

P.P.S. If you are just getting started, jump to the [new machine setup section](https://github.com/saraford/impostor-syndrome-walkthrough-of-github/blob/master/README.md#part-6---new-machine-setup-in-case-you-are-new-here). 

## Part 1 - Visualizing Git Commands

1. **GitHub offers an [excellent cheat sheet](https://education.github.com/git-cheat-sheet-education.pdf).** Print it out! 
2. **Setup your practice area using bash commands**
    - GitHub Services offers On Demand Training - shows [how to use a bash script](https://services.github.com/on-demand/git-trouble/git-set-up) to quickly create a test repo
    - Make sure to `git init` first!
    - See [Tip 086 for walkthrough](https://saraford.net/2017/03/27/how-to-write-a-bash-or-powershell-script-to-quickly-create-test-repos-086/)
3. **ohshitgit.com I've committed on master**
    - http://ohshitgit.com/#accidental-commit-master
4. **Git Visualization Tool**
    - A couple of GitHubbers created a [Git Visualization Tool](https://saraford.net/2017/03/22/how-to-demystify-git-commands-using-visualizing-git/)
    - This was my NEO WHOA moment - git branches are just pointers. 
    - Now to visualize what `git reset HEAD~ --hard` actually did 
    - See [Tip 082 for walkthrough](https://saraford.net/2017/03/23/how-to-fix-the-oh-no-ive-accidentally-committed-on-master-instead-of-a-branch-082/) 
5. **git reflog (cmd line vs visualization tool)**
    - Go back and demo in cmd line - OH NO MY FILES ARE GONE I HATE GIT IT IS THE WORST WHY DIDN'T I SAY IN AREOSPACE ENGINEERING WHY DID I MAKE SO MANY BAD CHOICES IN LIFE
    - Remember your training - go back to the visualization tool. notice the commits are still there, but with a dashed line.
    - See [Tip 87 for walkthrough](https://saraford.net/2017/03/28/how-to-recover-from-the-oh-no-i-did-a-git-reset-and-now-my-files-are-gone-087/)
    - Demo reset in visualization tool, then git log. Notice we're all back to where we were before - remember these git branches are just pointers.
6. **Revert vs reset (demo in visualization tool)**
    - Revert - this doesn't change history. It creates a new commit. 
    - Reset - let's just pretend everything after this point never happened
    - And git reflog still shows the truth for both commands
    - See [Tip 084 for Revert walkthrough in command line / visualization tool](https://saraford.net/2017/03/25/how-to-use-git-revert-to-undo-a-previous-commit-084/) 
    - See [Tip 085 for Revert in Visual Studio](https://saraford.net/2017/03/26/how-to-revert-changes-in-visual-studio-085/) 
    - See [Tip 087 for Reset walkthrough](https://saraford.net/2017/03/28/how-to-recover-from-the-oh-no-i-did-a-git-reset-and-now-my-files-are-gone-087/)
7. **Merging branches in visualization tool**
    - I always speak in full sentences. "I want to merge <branch> into <my current branch>"  
    - visualization tool can't do a --no-ff (no fast forwards)
    - See [Tip 088 for walkthrough](https://saraford.net/2017/03/29/how-to-create-a-branch-in-visual-studio-088/)
8. **You can do an Undo in the visualization tool**
    - if you're following along at home, type `undo` in tool. you'll go back to the point before the branch merge
9. **Rebase**
    - "I want to rebase <branch> onto <my current branch>"    
    - Note how rebase is a destructive action - the commit ids are different 
    - Not done yet! After rebase, have to move master up (same as merging branches)
      - Git checkout master; git merge feature
    - See [Tip 111 for cmd line walkthrough](https://saraford.net/2017/04/21/how-to-visualize-a-rebase-in-the-git-visualization-tool-111/) 
    - See [Tip 114 for Visual Studio walkthrough](https://saraford.net/2017/04/24/how-to-do-a-rebase-in-visual-studio-114/)
10. **Cherry-pick in visualization tool**
    - Switch to cherry-pick
    - git cherry-pick bugfix1
11. **Detatched Head** 
    - Do a `git checkout <some commit id>` and freak out that you're in a detatched head state
    - Do a `git checkout master` to calm back down and stay in your current profession
    - One thing about git that drives me crazy is when you checkout the commit id that master is pointing to, but yet are still in a detatched head state. After seeing this demo'ed in the visualization tool, I felt for hte first time I had a fighting chance using git. 
12. **Limitations of the tool**
    - No working directory, so no way to do interactive rebase
    - no reset `--hard` or `--soft`
13. **More GitHub Tutorials**
    - [GitHub Services On Demand Git Out Of Trouble](https://services.github.com/on-demand/git-trouble/)
    - Note: This tutorial offers "I've pushed" and "I've didn't push" guidance which is awesome!
    
## Part 2 - GitHub.com the website 

1. **How to see if my email address is in a commit that's already on GitHub?**
    - Go to the commit 
    - add `.patch` to the end of the URL
    - See [Tip 051 for walkthrough](https://saraford.net/2017/02/20/how-to-view-the-name-and-email-that-is-associated-with-a-commit-on-github-via-the-web-browser-051/)
2. **GitHub Keyboard Shortcuts**
    - Press `?` from on the page
    - On Code page
      - press 't' to start type-ahead search
      - Permalink 'y' - for a permalink to the blob (if you link to master, and file is updated, it'll be out of context)
    - Issues 
      - '/' to start searching
      - 'ctrl+shift+p' - toggle preview, but for Issues only    
    -  See [Tip 013 for shortcut walkthrough](https://saraford.net/2017/01/13/how-to-view-all-github-keyboard-shortcuts-013/)
    -  See [Tip 052 for permalink walkthroug](https://saraford.net/2017/02/21/how-to-press-y-to-navigate-to-the-permalink-for-a-files-exact-commit-id-on-github-com-052/)
3. **Protect your email address**
    - Check the option to block pushes containing your private email address
4. **Pull Request UX** - what absolutely confused me originally
    - When you create a PR going through the edit a doc workflow, the branch is already created
    - You don't have to create this Pull Request immediately. You can "cancel out"
    - PRs are the **start of a conversation**
    - Just creating this PR doesn't mean I've submitted my homework
	  - You can still go back to the branch and make updates and see it updated in the PR
    - Inline comments or start review
    - BTW even if you are the only one working in the repo and want to merge branches via the UI, you still need to create a PR. PRs are the only way to get to merge button.
    - Can also do simple merge conflicts from the website now
5. **How to add License / Readme**
    - It is part of the codebase - not metadata - so license/readme follows the code around
    - Repo != Visual Studio solution
    - If you type in License you'll get a prompt
    - See [Tip 048 for adding license walkthrough](https://saraford.net/2017/02/17/how-to-add-a-license-to-a-repo-and-have-it-be-recognized-for-an-existing-github-repo-048/)
6. **Gists - code samples**
	- https://gist.github.com/
7. **Pages**
    - Can have a pages site for a repo, e.g. https://saraford.github.io/TheoryC
    - You might have seem sites like https://saraford.github.io/ which maps back to https://github.com/saraford/saraford.github.io
    - Jekyll - for static pages only
      - There's an API for pages
      - https://developer.github.com/v3/repos/pages/#request-a-page-build
      - I thought it might be fun to do the ToD blog as a Pages site, but remember Jekyll is only static content
8. **Blame**
    - TBH I initially didn't want to push my code up on github when I saw "Blame" - I didn't want people to make fun of my code by blaming it. True story
    - Shows the commit when this line or block of code was changed
    - Blame is called Annotate in Visual Studio 
    - See [Tip 059 for walkthrough](https://saraford.net/2017/02/28/how-to-use-blame-on-github-to-find-the-commit-that-changed-that-line-or-block-of-code-059/) 

## Part 3 - Windows info
1. **Desktop**
    - Do it for 2FA setup
    - It also changes the defaults from vi to notepad in some cases to give you a fighting chance
    - See [Tip 038 for walkthrough](https://saraford.net/2017/02/07/how-to-setup-your-github-credentials-and-handle-2fa-on-windows-using-github-desktop-038/)
2. **Git Shell**
    - wished I had known this when I originally signed up for 2FA 
    - [Tip 038 for walkthrough](https://saraford.net/2017/02/07/how-to-setup-your-github-credentials-and-handle-2fa-on-windows-using-github-desktop-038/)

## Part 4 - Visual Studio info
   - My ToD really turned into a VS Team Explorer blog

1. **Staging** 
   - same as git add, but within VS
   - See [Tip 068 for walkthrough](https://saraford.net/2017/03/09/how-to-stage-changes-in-visual-studio-in-separate-files-066/)
2. **Status bar for push, commit, view history, switch branches, etc.**
   - See [Tip 083 for walkthrough](https://saraford.net/2017/03/24/how-to-use-the-vs-status-bar-buttons-as-a-shortcut-to-team-explorer-panes-083/)
3. The GitHub Extension for VS is **not** the Team Explorer
   - There's git and then there's Team Explorer and then there's the GitHub extension
4. **GitHub Extension for Visual Studio**
   - Looks like it is safe now to have an existing github repo and push it to a newly created GitHub repo without having to worry about different histories when pushing. 
   - "Maintainer workflow" - ability to review and modify PRs from within Visual Studio
   - See [Tip 066 for walkthrough](https://saraford.net/2017/03/07/how-to-use-the-github-tool-window-to-make-changes-to-a-pull-request-from-a-contributor-in-visual-studio-066/)
   
## Part 5 - Miscellaneous stuff

1. **[GitHub Plugin for Unity](https://unity.github.com)** 
2. **[Hololens walkthrough](https://saraford.net/2017/03/10/developing-my-first-hololens-app/)** 
3. **[Octodex](https://octodex.github.com)** 
4. **[Hubot](https://hubot.github.com)** 
5. **[Git.io link shortener](https://github.com/blog/985-git-io-github-url-shortener)** 

## Part 6 - New Machine Setup (in case you are new here)

1. **[Desktop / Git Shell](https://saraford.net/2017/02/07/how-to-setup-your-github-credentials-and-handle-2fa-on-windows-using-github-desktop-038/)**
2. **[Configure email](https://help.github.com/articles/setting-your-commit-email-address-in-git/)** / **[setup as private](https://github.com/blog/2346-private-emails-now-more-private)**
3. **Configure external diff and merge tool**
     - [command line](https://saraford.net/2017/04/14/how-to-configure-an-external-diff-and-merge-tool-in-git-104/)
     - [Visual Studio as external difftool](https://saraford.net/2017/04/15/how-to-use-visual-studio-as-your-external-git-difftool-105/)
     - [Visual Studio as external merge tool](https://saraford.net/2017/04/16/how-to-use-visual-studio-as-your-external-merge-tool-106/)
4. **[Verify core editor (anything but vi)](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)**
