# Azure DevOps & GitHub Actions Interview Questions and Answers

<div align="center">
  <img src="saanvik it_01.png" alt="Saanvik IT Logo" width="600"/>
  <h1>Azure DevOps & GitHub Actions Interview Questions and Answers</h1>
  <p><em>A comprehensive guide to prepare for DevOps technical interviews</em></p>
  <p><strong>Website:</strong> <a href="https://saanvikit.com">https://saanvikit.com</a> | <strong>Contact:</strong> +91 9513184144</p>
  <hr>
</div>

## Table of Contents
- [Development Process & Version Control](#development-process--version-control) (Questions 1-15)
- [Azure Pipelines](#azure-pipelines) (Questions 16-33)
- [GitHub Actions](#github-actions) (Questions 34-40)

<hr>

## Development Process & Version Control

### 1. What is the process you are using for your project? 🔄
<div class="answer">
<p>For our project, we follow an Agile development methodology with Scrum framework. This involves:</p>
<ul>
<li>Working in 2-week sprints with defined sprint goals</li>
<li>Daily stand-up meetings to discuss progress and blockers</li>
<li>Sprint planning at the beginning of each sprint</li>
<li>Sprint review and retrospective at the end</li>
<li>Maintaining a product backlog prioritized by the product owner</li>
<li>Using Azure DevOps/JIRA for tracking user stories, tasks, and bugs</li>
<li>Implementing CI/CD pipelines for continuous integration and delivery</li>
</ul>
<p>This process allows us to adapt quickly to changing requirements while maintaining a structured approach to development.</p>
</div>

### 2. Can you explain how the Agile process will work? 🔄
<div class="answer">
<p>The Agile process in our project works as follows:</p>
<ol>
<li><strong>Product Backlog Creation</strong>: The product owner creates and prioritizes the product backlog with user stories.</li>
<li><strong>Sprint Planning</strong>: The team selects items from the product backlog for the upcoming sprint and breaks them down into tasks.</li>
<li><strong>Daily Stand-ups</strong>: 15-minute daily meetings where team members discuss what they did yesterday, what they'll do today, and any blockers.</li>
<li><strong>Development Work</strong>: Team members pick up tasks from the sprint backlog and implement them following our coding standards.</li>
<li><strong>Continuous Integration</strong>: Code is frequently committed, built, and tested automatically.</li>
<li><strong>Sprint Review</strong>: At the end of the sprint, the team demonstrates completed work to stakeholders for feedback.</li>
<li><strong>Sprint Retrospective</strong>: The team reflects on the sprint, discussing what went well and what could be improved.</li>
<li><strong>Rinse and Repeat</strong>: The process continues with the next sprint planning.</li>
</ol>
<p>Throughout this process, we maintain transparency with visual boards, burndown charts, and regular communication with stakeholders.</p>
</div>

### 3. What is version control and why do we need it? 📚
<div class="answer">
<p>Version control is a system that records changes to files over time so you can recall specific versions later. It's essential for software development for several reasons:</p>
<ul>
<li><strong>History Tracking</strong>: Maintains a complete history of changes, who made them, and why.</li>
<li><strong>Collaboration</strong>: Enables multiple developers to work on the same codebase simultaneously without conflicts.</li>
<li><strong>Branching & Merging</strong>: Allows developers to create branches for features or fixes, then merge them back into the main codebase.</li>
<li><strong>Backup & Recovery</strong>: Serves as a backup mechanism, allowing recovery from mistakes or hardware failures.</li>
<li><strong>Traceability</strong>: Links changes to requirements, issues, or bug reports for better project management.</li>
<li><strong>Experimentation</strong>: Provides a safe environment to try new ideas without risking the stable codebase.</li>
<li><strong>Release Management</strong>: Facilitates tagging specific versions for release and maintaining multiple release versions.</li>
</ul>
<p>Without version control, coordinating work among team members would be chaotic, risky, and inefficient.</p>
</div>

### 4. Is Git centralized VC or distributed VC? 🌐
<div class="answer">
<p>Git is a <strong>distributed version control system (DVCS)</strong>. This means:</p>
<ul>
<li>Every developer has a complete copy of the repository, including its full history.</li>
<li>Developers can work offline and commit changes locally without needing a connection to a central server.</li>
<li>Changes can be shared between any two repositories without requiring a central hub.</li>
<li>There's no single point of failure, as each clone is a full backup of the repository.</li>
</ul>
<p>This is in contrast to centralized version control systems (like SVN or CVS) where a single server contains all versioned files, and clients check out files from that central place.</p>
<p>While Git is distributed by nature, many teams use it in a centralized manner with platforms like GitHub, GitLab, or Azure DevOps serving as the primary remote repository.</p>
</div>

### 5. What is the Git global config and why do we use it? ⚙️
<div class="answer">
<p>Git global config is a set of configuration variables that apply to all Git repositories on your system. It's stored in the <code>~/.gitconfig</code> file (or <code>C:\\Users\\&lt;username&gt;\\.gitconfig</code> on Windows).</p>
<p>We use Git global config to:</p>
<ul>
<li><strong>Set user identity</strong>: Configure your name and email that will appear in commit messages:
<pre><code>git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"</code></pre></li>
<li><strong>Set default editor</strong>: Specify which text editor Git should use:
<pre><code>git config --global core.editor "code --wait"</code></pre></li>
<li><strong>Configure line endings</strong>: Set how Git should handle line endings:
<pre><code>git config --global core.autocrlf true</code></pre></li>
<li><strong>Set default branch name</strong>: Define the default branch name for new repositories:
<pre><code>git config --global init.defaultBranch main</code></pre></li>
<li><strong>Create aliases</strong>: Define shortcuts for common Git commands:
<pre><code>git config --global alias.co checkout</code></pre></li>
<li><strong>Configure authentication</strong>: Set credential helpers for storing passwords or tokens.</li>
</ul>
<p>Using global config saves time by applying consistent settings across all repositories, eliminating the need to configure each repository individually.</p>
</div>

### 6. What is the command to clone a remote repo to local? 📥
<div class="answer">
<p>The command to clone a remote repository to your local machine is:</p>
<pre><code>git clone &lt;repository-url&gt;</code></pre>
<p>For example:</p>
<pre><code>git clone https://github.com/username/repository.git</code></pre>
<p>You can also specify a different directory name for the local repository:</p>
<pre><code>git clone https://github.com/username/repository.git my-folder</code></pre>
<p>For private repositories, you might need to authenticate:</p>
<ul>
<li>HTTPS: You'll be prompted for credentials or can include them in the URL</li>
<li>SSH: <code>git clone git@github.com:username/repository.git</code> (requires SSH key setup)</li>
</ul>
<p>Additional useful clone options include:</p>
<ul>
<li><code>--branch &lt;branch-name&gt;</code> or <code>-b &lt;branch-name&gt;</code>: Clone a specific branch</li>
<li><code>--depth &lt;depth&gt;</code>: Create a shallow clone with limited history</li>
<li><code>--single-branch</code>: Clone only a single branch</li>
</ul>
</div>

### 7. What are Git commands that you are aware of? 🛠️
<div class="answer">
<p>Common Git commands I use regularly include:</p>
<ul>
<li><strong>Setup and Configuration</strong>:
  <ul>
    <li><code>git config</code>: Configure Git settings</li>
    <li><code>git init</code>: Initialize a new Git repository</li>
    <li><code>git clone</code>: Clone a repository</li>
  </ul>
</li>
<li><strong>Basic Snapshotting</strong>:
  <ul>
    <li><code>git add</code>: Add files to staging area</li>
    <li><code>git status</code>: Check repository status</li>
    <li><code>git commit</code>: Commit staged changes</li>
    <li><code>git reset</code>: Reset staging area or commits</li>
    <li><code>git rm</code>: Remove files from working directory and staging area</li>
    <li><code>git mv</code>: Move or rename files</li>
  </ul>
</li>
<li><strong>Branching and Merging</strong>:
  <ul>
    <li><code>git branch</code>: List, create, or delete branches</li>
    <li><code>git checkout</code>: Switch branches or restore files</li>
    <li><code>git switch</code>: Switch branches (newer alternative to checkout)</li>
    <li><code>git merge</code>: Merge branches</li>
    <li><code>git rebase</code>: Reapply commits on another branch</li>
    <li><code>git cherry-pick</code>: Apply specific commits to current branch</li>
  </ul>
</li>
<li><strong>Sharing and Updating</strong>:
  <ul>
    <li><code>git fetch</code>: Download objects and refs from remote</li>
    <li><code>git pull</code>: Fetch and integrate with local repository</li>
    <li><code>git push</code>: Update remote refs and objects</li>
    <li><code>git remote</code>: Manage remote repositories</li>
  </ul>
</li>
<li><strong>Inspection and Comparison</strong>:
  <ul>
    <li><code>git log</code>: Show commit history</li>
    <li><code>git diff</code>: Show changes between commits, commit and working tree, etc.</li>
    <li><code>git show</code>: Show various types of objects</li>
    <li><code>git blame</code>: Show who changed what and when in a file</li>
  </ul>
</li>
<li><strong>Advanced Operations</strong>:
  <ul>
    <li><code>git stash</code>: Stash changes for later use</li>
    <li><code>git tag</code>: Create, list, delete, or verify tags</li>
    <li><code>git worktree</code>: Manage multiple working trees</li>
    <li><code>git bisect</code>: Use binary search to find a bad commit</li>
  </ul>
</li>
</ul>
<p>These commands form the core of my daily Git workflow, allowing me to manage code changes effectively across projects and teams.</p>
</div>

### 8. What is the difference between git fetch vs git pull? 🔄
<div class="answer">
<p>The main difference between <code>git fetch</code> and <code>git pull</code> is how they update your local repository with changes from a remote repository:</p>

<p><strong>git fetch</strong>:</p>
<ul>
<li>Downloads new data from the remote repository but doesn't integrate it into your working files</li>
<li>Updates your remote-tracking branches (e.g., origin/main)</li>
<li>Doesn't modify your working directory or local branches</li>
<li>Allows you to see what others have done without merging those changes</li>
<li>Is a safe way to review changes before integrating them</li>
</ul>
<pre><code>git fetch origin</code></pre>

<p><strong>git pull</strong>:</p>
<ul>
<li>Is essentially a <code>git fetch</code> followed by a <code>git merge</code> or <code>git rebase</code></li>
<li>Downloads new data from the remote repository AND immediately updates your current branch with those changes</li>
<li>Modifies your working directory to reflect the latest changes</li>
<li>Can cause merge conflicts if local changes conflict with remote changes</li>
</ul>
<pre><code>git pull origin main</code></pre>

<p>In practice:</p>
<ul>
<li>Use <code>git fetch</code> when you want to see what changes exist in the remote without applying them</li>
<li>Use <code>git pull</code> when you're ready to incorporate remote changes into your current branch</li>
<li>A common workflow is to <code>git fetch</code> first to review changes, then <code>git merge</code> or <code>git pull</code> when ready</li>
</ul>
</div>

### 9. What is git cherry-pick? 🍒
<div class="answer">
<p><code>git cherry-pick</code> is a command that allows you to apply a specific commit from one branch to another. It takes the changes introduced in a commit and creates a new commit with those same changes on your current branch.</p>

<p>Use cases for cherry-pick include:</p>
<ul>
<li>Applying a bug fix from one branch to another without merging the entire branch</li>
<li>Backporting features or fixes to maintenance branches</li>
<li>Recovering specific commits from a branch that was accidentally deleted</li>
<li>Selectively applying changes when a full merge isn't appropriate</li>
</ul>

<p>Basic usage:</p>
<pre><code>git cherry-pick &lt;commit-hash&gt;</code></pre>

<p>For example:</p>
<pre><code>git cherry-pick abc123</code></pre>

<p>Additional options:</p>
<ul>
<li><code>-n</code> or <code>--no-commit</code>: Apply changes without creating a commit</li>
<li><code>-e</code> or <code>--edit</code>: Edit the commit message before committing</li>
<li><code>-x</code>: Append "cherry-picked from commit..." to the commit message</li>
<li><code>-s</code> or <code>--signoff</code>: Add a "Signed-off-by" line to the commit message</li>
<li><code>--continue</code>, <code>--abort</code>, <code>--quit</code>: Control cherry-pick process after conflicts</li>
</ul>

<p>Cherry-picking multiple commits:</p>
<pre><code>git cherry-pick &lt;commit-hash1&gt; &lt;commit-hash2&gt;</code></pre>
<p>Or a range of commits:</p>
<pre><code>git cherry-pick &lt;start-commit&gt;..&lt;end-commit&gt;</code></pre>

<p>Note that cherry-picking creates new commits with different hashes than the original commits, which can potentially cause conflicts if the same changes are later merged through other means.</p>
</div>

### 10. What is the git branching strategy that you are following for your project? 🌿
<div class="answer">
<p>For our project, we follow the GitFlow branching strategy, which provides a robust framework for managing larger projects. Our implementation includes:</p>

<ul>
<li><strong>Main/Master branch</strong>: Contains production-ready code. Only stable, tested code is merged here.</li>
<li><strong>Develop branch</strong>: Our integration branch where features are combined for testing before release.</li>
<li><strong>Feature branches</strong>: Created from develop for new features or enhancements. Naming convention: <code>feature/feature-name</code></li>
<li><strong>Release branches</strong>: Created from develop when preparing a new production release. Used for final testing and bug fixes. Naming: <code>release/version-number</code></li>
<li><strong>Hotfix branches</strong>: Created from main/master to quickly address critical production issues. Naming: <code>hotfix/issue-description</code></li>
<li><strong>Bugfix branches</strong>: For non-critical bugs found during development. Branched from develop. Naming: <code>bugfix/issue-description</code></li>
</ul>

<p>Our workflow follows these steps:</p>
<ol>
<li>Developers create feature branches from develop</li>
<li>When features are complete, they're merged back to develop via pull requests</li>
<li>When develop has enough features for a release, a release branch is created</li>
<li>After testing and bug fixes, the release branch is merged to both main/master and develop</li>
<li>If issues are found in production, hotfix branches are created from main/master</li>
<li>Hotfixes are merged to both main/master and develop</li>
</ol>

<p>This strategy helps us maintain a clean repository history, enables parallel development, and provides a structured approach to releases and hotfixes.</p>
</div>
### 11. What are the branching policies and what policies do you have for your project? 🔒
<div class="answer">
<p>Branching policies are rules that enforce code quality and change management practices when code is pushed to specific branches. In our project, we implement the following policies:</p>

<p><strong>For the main/master branch:</strong></p>
<ul>
<li><strong>Require pull requests</strong>: Direct commits to main are prohibited; all changes must come through reviewed PRs</li>
<li><strong>Minimum number of reviewers</strong>: At least 2 senior developers must approve changes</li>
<li><strong>Linked work items</strong>: Each PR must be linked to a work item (user story, bug, or task)</li>
<li><strong>Build validation</strong>: CI build must succeed before PR can be completed</li>
<li><strong>Required code coverage</strong>: Maintain minimum 80% code coverage</li>
<li><strong>Comment resolution</strong>: All comments must be resolved before merging</li>
</ul>

<p><strong>For the develop branch:</strong></p>
<ul>
<li><strong>Require pull requests</strong>: Direct commits prohibited</li>
<li><strong>Minimum number of reviewers</strong>: At least 1 developer must approve</li>
<li><strong>Build validation</strong>: CI build must succeed</li>
<li><strong>Comment resolution</strong>: All comments must be resolved</li>
</ul>

<p><strong>For feature branches:</strong></p>
<ul>
<li><strong>Naming convention enforcement</strong>: Must follow pattern <code>feature/feature-name</code></li>
<li><strong>Branch cleanup</strong>: Automatic deletion after merging</li>
</ul>

<p>These policies help us maintain code quality, ensure proper review processes, and create a clear audit trail of changes throughout the development lifecycle.</p>
</div>

### 12. What are Git tags? 🏷️
<div class="answer">
<p>Git tags are references that point to specific points in Git history, typically used to mark release points (v1.0, v2.0, etc.). Unlike branches, tags don't change once created - they're snapshots that always point to the same commit.</p>

<p>There are two types of Git tags:</p>
<ul>
<li><strong>Lightweight tags</strong>: Simply a pointer to a specific commit</li>
<li><strong>Annotated tags</strong>: Stored as full objects in the Git database, containing the tagger's name, email, date, and a tagging message</li>
</ul>

<p>Common uses for tags include:</p>
<ul>
<li>Marking release versions (v1.0.0, v2.1.3)</li>
<li>Creating stable reference points in development history</li>
<li>Identifying significant milestones in a project</li>
</ul>

<p>Basic tag commands:</p>
<pre><code># Create a lightweight tag
git tag v1.0.0

# Create an annotated tag
git tag -a v1.0.0 -m "Version 1.0.0 release"

# List all tags
git tag

# Push tags to remote
git push origin --tags

# Delete a tag
git tag -d v1.0.0

# Delete a remote tag
git push origin --delete v1.0.0

# Check out code at a specific tag
git checkout v1.0.0
</code></pre>

<p>In our CI/CD pipelines, we often use tags to trigger release processes and to maintain a clear history of what code was included in each release.</p>
</div>

### 13. What is the command used to create a branch? 🌱
<div class="answer">
<p>The command to create a new branch in Git is:</p>
<pre><code>git branch &lt;branch-name&gt;</code></pre>

<p>This creates a new branch but doesn't switch to it. To create a branch and switch to it in one command, use:</p>
<pre><code>git checkout -b &lt;branch-name&gt;</code></pre>

<p>In newer versions of Git (2.23+), you can also use:</p>
<pre><code>git switch -c &lt;branch-name&gt;</code></pre>

<p>To create a branch from a specific commit or reference:</p>
<pre><code>git branch &lt;branch-name&gt; &lt;commit-hash&gt;
git checkout -b &lt;branch-name&gt; &lt;commit-hash&gt;
git switch -c &lt;branch-name&gt; &lt;commit-hash&gt;</code></pre>

<p>To create a branch from a remote branch:</p>
<pre><code>git checkout -b &lt;local-branch-name&gt; origin/&lt;remote-branch-name&gt;
git switch -c &lt;local-branch-name&gt; origin/&lt;remote-branch-name&gt;</code></pre>

<p>To push the new branch to the remote repository:</p>
<pre><code>git push -u origin &lt;branch-name&gt;</code></pre>

<p>The <code>-u</code> flag sets up tracking, which links your local branch to the remote branch, making subsequent push and pull operations simpler.</p>
</div>

### 14. What is the command to delete a branch? 🗑️
<div class="answer">
<p>To delete a branch in Git, you can use the following commands:</p>

<p><strong>Delete a local branch:</strong></p>
<pre><code># Delete a fully merged branch
git branch -d &lt;branch-name&gt;

# Force delete a branch (even if not merged)
git branch -D &lt;branch-name&gt;</code></pre>

<p><strong>Delete a remote branch:</strong></p>
<pre><code># Modern syntax
git push origin --delete &lt;branch-name&gt;

# Alternative syntax
git push origin :&lt;branch-name&gt;</code></pre>

<p><strong>Delete multiple branches:</strong></p>
<pre><code># Delete multiple local branches
git branch -d branch1 branch2 branch3

# Delete all local branches except main
git branch | grep -v "main" | xargs git branch -D</code></pre>

<p><strong>Clean up tracking branches:</strong></p>
<pre><code># Remove local references to remote branches that no longer exist
git fetch --prune
# or
git remote prune origin</code></pre>

<p>It's important to note that you cannot delete the branch you're currently on. You need to switch to another branch first using <code>git checkout</code> or <code>git switch</code>.</p>

<p>In our workflow, we typically delete feature branches after they've been merged to maintain a clean repository.</p>
</div>

### 15. What is git log? 📜
<div class="answer">
<p><code>git log</code> is a command that displays the commit history of a repository. It shows a list of commits made in the repository in reverse chronological order (most recent commits first).</p>

<p>Basic usage:</p>
<pre><code>git log</code></pre>

<p>Each commit entry typically shows:</p>
<ul>
<li>Commit hash (SHA-1 identifier)</li>
<li>Author name and email</li>
<li>Date and time of the commit</li>
<li>Commit message</li>
</ul>

<p>Useful options and variations:</p>
<pre><code># Show a specific number of commits
git log -n 5

# Show commits with patches (diffs)
git log -p

# Show statistics for each commit
git log --stat

# Show commits in a condensed one-line format
git log --oneline

# Show a graph of branches and merges
git log --graph --oneline --all

# Show commits by a specific author
git log --author="John Doe"

# Show commits between dates
git log --since="2023-01-01" --until="2023-12-31"

# Show commits that changed a specific file
git log -- path/to/file

# Show commits with a specific message pattern
git log --grep="bug fix"

# Show commits that added or removed specific code
git log -S"function_name"</code></pre>

<p>In our development workflow, we use <code>git log</code> to:</p>
<ul>
<li>Track changes to specific features or components</li>
<li>Identify when and why particular changes were made</li>
<li>Find commits that may have introduced bugs</li>
<li>Review the development history before making changes</li>
<li>Generate release notes by summarizing commits between versions</li>
</ul>
</div>

## Azure Pipelines

### 16. What are Azure Pipelines and why do we use them? 🔄
<div class="answer">
<p>Azure Pipelines is a cloud service that provides CI/CD (Continuous Integration and Continuous Delivery) capabilities as part of Azure DevOps. It allows you to automatically build, test, and deploy your code to any platform or cloud.</p>

<p><strong>Key features:</strong></p>
<ul>
<li><strong>Language and platform agnostic</strong>: Supports virtually any language, platform, or cloud</li>
<li><strong>Deployment targets</strong>: Can deploy to VMs, containers, on-premises, Azure services, or any cloud</li>
<li><strong>Extensible</strong>: Rich marketplace with extensions and integrations</li>
<li><strong>Parallel execution</strong>: Run multiple jobs in parallel</li>
<li><strong>YAML or visual designer</strong>: Define pipelines as code or through UI</li>
<li><strong>Reusable templates</strong>: Create standardized pipeline components</li>
<li><strong>Release gates</strong>: Add approval checks before deployment</li>
<li><strong>Integration with Azure services</strong>: Seamless connection with other Azure resources</li>
</ul>

<p><strong>Why we use Azure Pipelines:</strong></p>
<ul>
<li><strong>Automation</strong>: Eliminates manual build and deployment processes</li>
<li><strong>Consistency</strong>: Ensures builds and deployments are performed the same way every time</li>
<li><strong>Early feedback</strong>: Quickly identifies issues through automated testing</li>
<li><strong>Traceability</strong>: Links builds and releases to work items and code changes</li>
<li><strong>Quality control</strong>: Enforces quality gates before code reaches production</li>
<li><strong>Reduced risk</strong>: Smaller, more frequent releases minimize deployment risk</li>
<li><strong>Infrastructure as Code</strong>: Manages pipeline configuration in version control</li>
<li><strong>Scalability</strong>: Handles multiple projects and teams with varying needs</li>
</ul>

<p>In our projects, Azure Pipelines forms the backbone of our DevOps practices, enabling us to deliver high-quality software rapidly and reliably.</p>
</div>

### 17. What is the difference between Microsoft-hosted agent vs self-hosted agent pools? 🖥️
<div class="answer">
<p>Azure Pipelines offers two types of build and deployment agents: Microsoft-hosted and self-hosted. Each has distinct characteristics that make them suitable for different scenarios.</p>

<p><strong>Microsoft-hosted agents:</strong></p>
<ul>
<li><strong>Management</strong>: Fully managed by Microsoft; no maintenance required</li>
<li><strong>Clean environment</strong>: Fresh VM for each pipeline run</li>
<li><strong>Pre-installed software</strong>: Common development tools already available</li>
<li><strong>OS options</strong>: Windows, Linux, and macOS</li>
<li><strong>Scalability</strong>: Automatically scales based on demand</li>
<li><strong>Limitations</strong>: 
  <ul>
    <li>Limited run time (typically 6 hours)</li>
    <li>Limited disk space</li>
    <li>No custom software unless installed during the pipeline</li>
    <li>No access to on-premises resources without additional configuration</li>
  </ul>
</li>
<li><strong>Cost</strong>: Included minutes with Azure DevOps, pay for additional usage</li>
</ul>

<p><strong>Self-hosted agents:</strong></p>
<ul>
<li><strong>Management</strong>: You provision and maintain the infrastructure</li>
<li><strong>Environment</strong>: Persistent between runs (unless you implement cleanup)</li>
<li><strong>Software</strong>: Complete control over installed tools and versions</li>
<li><strong>Location</strong>: Can be deployed anywhere (on-premises, cloud VMs, containers)</li>
<li><strong>Network access</strong>: Direct access to on-premises resources</li>
<li><strong>Customization</strong>: Full control over hardware specifications</li>
<li><strong>No time limits</strong>: Run as long as needed</li>
<li><strong>Cost</strong>: You pay for the infrastructure, but pipeline minutes are free</li>
</ul>

<p><strong>When we use each type:</strong></p>
<ul>
<li><strong>Microsoft-hosted</strong>:
  <ul>
    <li>Open-source projects</li>
    <li>Standard development environments</li>
    <li>Projects with minimal special requirements</li>
    <li>When maintenance overhead needs to be minimized</li>
  </ul>
</li>
<li><strong>Self-hosted</strong>:
  <ul>
    <li>When we need access to on-premises resources</li>
    <li>For specialized build requirements or custom software</li>
    <li>When we need more powerful hardware than Microsoft-hosted provides</li>
    <li>For longer-running jobs</li>
    <li>When we need to cache large dependencies between runs</li>
  </ul>
</li>
</ul>

<p>In our environment, we use a combination of both: Microsoft-hosted agents for standard builds and self-hosted agents for deployments that require access to our internal network resources.</p>
</div>

### 18. What is a service connection? 🔌
<div class="answer">
<p>A service connection in Azure DevOps is a stored set of credentials and configuration details that allows your pipelines to securely connect to and interact with external services and resources.</p>

<p><strong>Common types of service connections:</strong></p>
<ul>
<li><strong>Azure Resource Manager</strong>: Connect to Azure subscriptions</li>
<li><strong>GitHub/GitHub Enterprise</strong>: Connect to GitHub repositories</li>
<li><strong>Docker Registry</strong>: Connect to container registries like Docker Hub or Azure Container Registry</li>
<li><strong>Kubernetes</strong>: Connect to Kubernetes clusters</li>
<li><strong>Maven/npm</strong>: Connect to package repositories</li>
<li><strong>SSH</strong>: Connect to servers using SSH</li>
<li><strong>Service Fabric</strong>: Connect to Service Fabric clusters</li>
<li><strong>Jenkins</strong>: Connect to Jenkins servers</li>
<li><strong>Bitbucket/GitLab</strong>: Connect to other Git providers</li>
<li><strong>SonarQube</strong>: Connect to SonarQube servers for code analysis</li>
</ul>

<p><strong>Key aspects of service connections:</strong></p>
<ul>
<li><strong>Security</strong>: Credentials are encrypted and securely stored</li>
<li><strong>Scoping</strong>: Can be scoped to specific projects or shared across an organization</li>
<li><strong>Permissions</strong>: Access can be controlled through Azure DevOps security groups</li>
<li><strong>Reusability</strong>: Can be referenced across multiple pipelines</li>
<li><strong>Validation</strong>: Connections are validated when created</li>
<li><strong>Service Principal</strong>: Often use Azure AD service principals for authentication</li>
<li><strong>Approval workflows</strong>: Can require approval for usage in pipelines</li>
</ul>

<p><strong>How we use service connections:</strong></p>
<ul>
<li>Creating ARM service connections for deploying to different Azure environments (dev, test, prod)</li>
<li>Setting up Docker Registry connections for pushing container images</li>
<li>Configuring GitHub connections for source code access</li>
<li>Establishing Kubernetes connections for deploying to AKS clusters</li>
<li>Setting up SonarQube connections for code quality analysis</li>
</ul>

<p>Service connections are defined in the Project Settings section of Azure DevOps and are referenced in pipeline YAML or classic editor by name.</p>
</div>

### 19. What are the pre-requisites to set up a pipeline? 🛠️
<div class="answer">
<p>Setting up an Azure Pipeline requires several prerequisites to ensure successful implementation:</p>

<p><strong>1. Source Code Repository</strong></p>
<ul>
<li>Code hosted in a supported repository (Azure Repos, GitHub, Bitbucket, etc.)</li>
<li>Appropriate permissions to access the repository</li>
<li>Ideally, a well-structured project with a clear build process</li>
</ul>

<p><strong>2. Azure DevOps Organization and Project</strong></p>
<ul>
<li>An Azure DevOps organization</li>
<li>A project within that organization</li>
<li>Appropriate permissions (Build Administrator or Project Administrator)</li>
</ul>

<p><strong>3. Pipeline Configuration</strong></p>
<ul>
<li>YAML pipeline definition file (azure-pipelines.yml) or knowledge to create one</li>
<li>Understanding of the build and deployment requirements</li>
<li>Familiarity with the application architecture</li>
</ul>

<p><strong>4. Build Agents</strong></p>
<ul>
<li>Decision on whether to use Microsoft-hosted or self-hosted agents</li>
<li>For self-hosted agents: appropriate hardware, network access, and agent installation</li>
<li>Sufficient parallel jobs available in your Azure DevOps plan</li>
</ul>

<p><strong>5. Service Connections</strong></p>
<ul>
<li>Required service connections configured for external services</li>
<li>Appropriate credentials and permissions for those services</li>
<li>For Azure deployments: service principal with appropriate RBAC permissions</li>
</ul>

<p><strong>6. Deployment Targets</strong></p>
<ul>
<li>Configured environments for deployment</li>
<li>Network connectivity between agents and deployment targets</li>
<li>Required permissions on target environments</li>
</ul>

<p><strong>7. Additional Requirements</strong></p>
<ul>
<li>Variable groups or secure files for storing secrets</li>
<li>Artifact feeds for package management</li>
<li>Test environments for automated testing</li>
<li>Approval policies and security checks if required</li>
</ul>

<p>In our organization, we maintain a checklist of these prerequisites to ensure smooth pipeline setup for new projects.</p>
</div>

### 20. Explain the CI/CD flow of your project 🔄
<div class="answer">
<p>Our project follows a comprehensive CI/CD flow that automates the entire process from code commit to production deployment. Here's how it works:</p>

<p><strong>Continuous Integration (CI) Flow:</strong></p>
<ol>
<li><strong>Code Commit</strong>: Developer commits code to a feature branch in our Git repository</li>
<li><strong>Pull Request</strong>: Developer creates a PR to merge changes into the develop branch</li>
<li><strong>Automated Build Trigger</strong>: PR creation automatically triggers a CI build pipeline</li>
<li><strong>Code Compilation</strong>: Source code is compiled and built</li>
<li><strong>Unit Testing</strong>: Automated unit tests are executed</li>
<li><strong>Code Analysis</strong>: SonarQube analyzes code for quality and security issues</li>
<li><strong>Security Scanning</strong>: Dependencies are scanned for vulnerabilities</li>
<li><strong>Build Artifacts</strong>: If all checks pass, build artifacts are created and published</li>
<li><strong>PR Validation</strong>: Build results are reported back to the PR</li>
<li><strong>Code Review</strong>: Team members review the code changes</li>
<li><strong>PR Completion</strong>: After approval, the PR is completed and merged to develop</li>
</ol>

<p><strong>Continuous Delivery (CD) Flow:</strong></p>
<ol>
<li><strong>Develop Branch Build</strong>: Successful merge to develop triggers another build</li>
<li><strong>Integration Testing</strong>: Automated integration tests are run</li>
<li><strong>Dev Environment Deployment</strong>: Artifacts are automatically deployed to the development environment</li>
<li><strong>QA Environment Deployment</strong>: After manual approval, deployment to QA environment occurs</li>
<li><strong>Automated Testing</strong>: Functional, performance, and UI tests run in QA</li>
<li><strong>Staging Deployment</strong>: After QA approval, deployment to staging environment</li>
<li><strong>UAT</strong>: User acceptance testing is performed in staging</li>
<li><strong>Release Creation</strong>: A release branch is created from develop</li>
<li><strong>Production Deployment</strong>: After final approval, deployment to production</li>
<li><strong>Post-Deployment Validation</strong>: Smoke tests verify production functionality</li>
<li><strong>Monitoring</strong>: Application performance and health are monitored</li>
</ol>

<p><strong>Key Features of Our CI/CD Pipeline:</strong></p>
<ul>
<li><strong>Infrastructure as Code</strong>: All environments are defined using Terraform</li>
<li><strong>Environment Parity</strong>: All environments have similar configurations</li>
<li><strong>Automated Rollback</strong>: Automatic rollback if deployment fails or tests fail</li>
<li><strong>Feature Flags</strong>: New features can be toggled on/off in production</li>
<li><strong>Blue-Green Deployments</strong>: Zero-downtime deployments for critical services</li>
<li><strong>Approval Gates</strong>: Required approvals before promoting to higher environments</li>
<li><strong>Compliance Checks</strong>: Automated checks for regulatory compliance</li>
</ul>

<p>This CI/CD flow ensures that our code is thoroughly tested and validated before reaching production, while still allowing for rapid delivery of new features and bug fixes.</p>
</div>

### 21. Tell me step by step how do you deploy Terraform via Azure Pipelines 🏗️
<div class="answer">
<p>Deploying Terraform infrastructure using Azure Pipelines involves several key steps. Here's my step-by-step approach:</p>

<p><strong>Step 1: Set up prerequisites</strong></p>
<ul>
<li>Terraform code in a repository (Azure Repos or GitHub)</li>
<li>Azure DevOps project with pipeline permissions</li>
<li>Service connection to Azure with appropriate permissions</li>
<li>Storage account for Terraform state (recommended)</li>
</ul>

<p><strong>Step 2: Create the pipeline YAML file</strong></p>
<p>Create an <code>azure-pipelines.yml</code> file in your repository:</p>

<pre><code>trigger:
  - main

pool:
  vmImage: 'ubuntu-latest'

variables:
  - group: terraform-variables
  - name: TF_WORKSPACE
    value: 'dev'

stages:
- stage: Validate
  jobs:
  - job: ValidateAndPlan
    steps:
    - task: TerraformInstaller@0
      inputs:
        terraformVersion: '1.5.0'
    
    - task: TerraformTaskV4@4
      inputs:
        provider: 'azurerm'
        command: 'init'
        workingDirectory: '$(System.DefaultWorkingDirectory)/terraform'
        backendServiceArm: 'azure-service-connection'
        backendAzureRmResourceGroupName: 'terraform-state-rg'
        backendAzureRmStorageAccountName: 'tfstate12345'
        backendAzureRmContainerName: 'tfstate'
        backendAzureRmKey: 'dev.terraform.tfstate'
    
    - task: TerraformTaskV4@4
      inputs:
        provider: 'azurerm'
        command: 'validate'
        workingDirectory: '$(System.DefaultWorkingDirectory)/terraform'
    
    - task: TerraformTaskV4@4
      inputs:
        provider: 'azurerm'
        command: 'plan'
        workingDirectory: '$(System.DefaultWorkingDirectory)/terraform'
        environmentServiceNameAzureRM: 'azure-service-connection'
        publishPlanResults: 'tfplan'

- stage: Apply
  dependsOn: Validate
  condition: succeeded()
  jobs:
  - deployment: ApplyTerraform
    environment: 'dev'
    strategy:
      runOnce:
        deploy:
          steps:
          - task: TerraformInstaller@0
            inputs:
              terraformVersion: '1.5.0'
          
          - task: TerraformTaskV4@4
            inputs:
              provider: 'azurerm'
              command: 'init'
              workingDirectory: '$(System.DefaultWorkingDirectory)/terraform'
              backendServiceArm: 'azure-service-connection'
              backendAzureRmResourceGroupName: 'terraform-state-rg'
              backendAzureRmStorageAccountName: 'tfstate12345'
              backendAzureRmContainerName: 'tfstate'
              backendAzureRmKey: 'dev.terraform.tfstate'
          
          - task: TerraformTaskV4@4
            inputs:
              provider: 'azurerm'
              command: 'apply'
              workingDirectory: '$(System.DefaultWorkingDirectory)/terraform'
              environmentServiceNameAzureRM: 'azure-service-connection'
              commandOptions: '-auto-approve'</code></pre>

<p><strong>Step 3: Set up Terraform state storage</strong></p>
<ol>
<li>Create a resource group for Terraform state</li>
<li>Create a storage account and container</li>
<li>Configure backend in your Terraform code or during init</li>
</ol>

<p><strong>Step 4: Create variable groups</strong></p>
<ol>
<li>In Azure DevOps, go to Pipelines > Library</li>
<li>Create a variable group named "terraform-variables"</li>
<li>Add necessary variables (ARM_CLIENT_ID, ARM_CLIENT_SECRET, etc.)</li>
<li>Link the variable group to your pipeline</li>
</ol>

<p><strong>Step 5: Configure environments and approvals</strong></p>
<ol>
<li>Create environments in Azure DevOps (dev, test, prod)</li>
<li>Set up approval gates for sensitive environments</li>
<li>Configure environment-specific variables</li>
</ol>

<p><strong>Step 6: Run the pipeline</strong></p>
<ol>
<li>Commit and push the pipeline YAML file</li>
<li>Create and run the pipeline in Azure DevOps</li>
<li>Review the Terraform plan output</li>
<li>Approve the deployment to proceed to apply stage</li>
</ol>

<p><strong>Step 7: Monitor and verify</strong></p>
<ol>
<li>Monitor the pipeline execution</li>
<li>Verify resources are created in Azure Portal</li>
<li>Check Terraform state file in storage account</li>
</ol>

<p><strong>Best practices we follow:</strong></p>
<ul>
<li>Use separate workspaces or state files for different environments</li>
<li>Store sensitive variables as secrets in variable groups</li>
<li>Implement drift detection in the pipeline</li>
<li>Use output variables to share information between stages</li>
<li>Include destroy jobs for cleaning up test environments</li>
<li>Version Terraform providers and modules</li>
</ul>
</div>

### 22. What is CI/CD? 🔄
<div class="answer">
<p>CI/CD stands for Continuous Integration and Continuous Delivery/Deployment, a set of practices that automate and streamline the software delivery process.</p>

<p><strong>Continuous Integration (CI)</strong> is the practice of frequently integrating code changes into a shared repository, followed by automated building and testing. Key aspects include:</p>
<ul>
<li>Developers regularly merge code changes into a central repository</li>
<li>Each integration is verified by automated builds and tests</li>
<li>Early detection of integration issues and bugs</li>
<li>Frequent code commits (typically multiple times per day)</li>
<li>Automated quality checks (unit tests, code analysis, etc.)</li>
<li>Fast feedback to developers about the quality of their changes</li>
</ul>

<p><strong>Continuous Delivery (CD)</strong> extends CI by automatically preparing code changes for release to production. Key aspects include:</p>
<ul>
<li>Automated deployment to testing and staging environments</li>
<li>Comprehensive automated testing (integration, system, acceptance)</li>
<li>Production-like environments for testing</li>
<li>Release-ready code that can be deployed at any time</li>
<li>Manual approval for production deployment</li>
<li>Consistent deployment process across environments</li>
</ul>

<p><strong>Continuous Deployment</strong> goes one step further by automatically deploying every change that passes all tests directly to production without manual intervention.</p>

<p><strong>Benefits of CI/CD:</strong></p>
<ul>
<li><strong>Faster time to market</strong>: Streamlined delivery process</li>
<li><strong>Higher quality</strong>: Automated testing catches issues early</li>
<li><strong>Reduced risk</strong>: Smaller, incremental changes are easier to troubleshoot</li>
<li><strong>Better collaboration</strong>: Frequent integration improves team coordination</li>
<li><strong>Increased productivity</strong>: Automation reduces manual tasks</li>
<li><strong>Reliable releases</strong>: Consistent, repeatable deployment process</li>
<li><strong>Customer satisfaction</strong>: Faster delivery of features and fixes</li>
</ul>

<p><strong>Key tools and practices in our CI/CD implementation:</strong></p>
<ul>
<li>Version control with Git</li>
<li>Azure Pipelines for build and release automation</li>
<li>Automated testing at multiple levels</li>
<li>Infrastructure as Code for environment consistency</li>
<li>Monitoring and observability tools</li>
<li>Feature flags for controlled feature rollout</li>
</ul>
</div>

### 23. What is the difference between continuous deployment vs continuous delivery? 🚀
<div class="answer">
<p>While both continuous deployment and continuous delivery are extensions of continuous integration, they differ in their approach to releasing software to production:</p>

<p><strong>Continuous Delivery:</strong></p>
<ul>
<li><strong>Definition</strong>: The practice of automatically preparing and testing code changes so they're ready for production deployment, but requiring a manual approval for the actual release</li>
<li><strong>Release process</strong>: Semi-automated with manual approval gate</li>
<li><strong>Human intervention</strong>: Required for production deployment</li>
<li><strong>Deployment frequency</strong>: On-demand, when business decides</li>
<li><strong>Risk level</strong>: Moderate, as human judgment is involved</li>
<li><strong>Suitable for</strong>: 
  <ul>
    <li>Regulated industries with compliance requirements</li>
    <li>Products where release timing is business-critical</li>
    <li>Systems where downtime must be carefully planned</li>
    <li>Teams transitioning from traditional to fully automated deployments</li>
  </ul>
</li>
</ul>

<p><strong>Continuous Deployment:</strong></p>
<ul>
<li><strong>Definition</strong>: The practice of automatically deploying every change that passes all tests directly to production without any manual intervention</li>
<li><strong>Release process</strong>: Fully automated end-to-end</li>
<li><strong>Human intervention</strong>: None for routine deployments</li>
<li><strong>Deployment frequency</strong>: Multiple times per day (with each validated change)</li>
<li><strong>Risk level</strong>: Managed through comprehensive automated testing</li>
<li><strong>Suitable for</strong>: 
  <ul>
    <li>Web and SaaS applications</li>
    <li>Products requiring rapid iteration</li>
    <li>Teams with mature testing practices</li>
    <li>Systems designed with zero-downtime deployment capabilities</li>
  </ul>
</li>
</ul>

<p><strong>Key differences:</strong></p>
<table>
  <tr>
    <th>Aspect</th>
    <th>Continuous Delivery</th>
    <th>Continuous Deployment</th>
  </tr>
  <tr>
    <td>Production deployment</td>
    <td>Manual decision</td>
    <td>Automatic</td>
  </tr>
  <tr>
    <td>Release cadence</td>
    <td>Business-driven</td>
    <td>Development-driven</td>
  </tr>
  <tr>
    <td>Testing requirements</td>
    <td>High</td>
    <td>Very high</td>
  </tr>
  <tr>
    <td>Feature flags</td>
    <td>Optional</td>
    <td>Often essential</td>
  </tr>
  <tr>
    <td>Rollback strategy</td>
    <td>Can be manual or automated</td>
    <td>Must be automated</td>
  </tr>
</table>

<p>In our organization, we primarily use continuous delivery for our core enterprise applications, requiring approval from product owners before production deployment. However, for our internal developer tools and some microservices, we've implemented continuous deployment to increase delivery velocity.</p>
</div>

### 24. What is library in Azure Pipelines? 📚
<div class="answer">
<p>A library in Azure Pipelines is a collection of shared resources that can be used across multiple pipelines. These resources help manage configuration data, secrets, and files that need to be accessed during pipeline execution.</p>

<p><strong>Key components of Azure Pipelines libraries:</strong></p>

<p><strong>1. Variable Groups</strong></p>
<ul>
<li>Collections of related variables stored together</li>
<li>Can be linked to Azure Key Vault for secure storage</li>
<li>Reusable across multiple pipelines</li>
<li>Support for environment-specific configurations</li>
<li>Can be updated without modifying pipeline definitions</li>
</ul>
<pre><code># Referencing a variable group in YAML pipeline
variables:
  - group: my-variable-group</code></pre>

<p><strong>2. Secure Files</strong></p>
<ul>
<li>Storage for files that need to be protected (certificates, key files, etc.)</li>
<li>Encrypted at rest and in transit</li>
<li>Access controlled through permissions</li>
<li>Available during pipeline execution but not exposed in logs</li>
<li>Common examples: SSL certificates, npm tokens, Java keystores</li>
</ul>
<pre><code># Using secure files in a pipeline task
steps:
- task: DownloadSecureFile@1
  name: sshKey
  inputs:
    secureFile: 'id_rsa'</code></pre>

<p><strong>3. Service Connections</strong></p>
<ul>
<li>Stored credentials for external services</li>
<li>Secure way to connect to deployment targets</li>
<li>Support for various service types (Azure, GitHub, Docker, etc.)</li>
<li>Can be shared across projects or limited to specific projects</li>
</ul>

<p><strong>Benefits of using libraries:</strong></p>
<ul>
<li><strong>Centralized management</strong>: Update values in one place</li>
<li><strong>Security</strong>: Proper handling of sensitive information</li>
<li><strong>Reusability</strong>: Share configurations across pipelines</li>
<li><strong>Separation of concerns</strong>: Keep pipeline definitions clean</li>
<li><strong>Environment support</strong>: Manage different values for different environments</li>
<li><strong>Auditability</strong>: Track changes to shared resources</li>
</ul>

<p><strong>How we use libraries in our projects:</strong></p>
<ul>
<li>Environment-specific variable groups (dev, test, prod)</li>
<li>Shared configuration variable groups (common settings)</li>
<li>Secure storage for certificates and connection strings</li>
<li>Service connections for different deployment targets</li>
<li>Secure files for deployment scripts and configuration templates</li>
</ul>

<p>Libraries are managed in the Azure DevOps portal under Pipelines > Library, where you can create, edit, and manage permissions for these resources.</p>
</div>

### 25. How do you maintain secrets in your pipeline? 🔒
<div class="answer">
<p>Maintaining secrets securely in Azure Pipelines is critical for protecting sensitive information. We use several approaches to manage secrets properly:</p>

<p><strong>1. Variable Groups with Azure Key Vault Integration</strong></p>
<ul>
<li>Link variable groups to Azure Key Vault</li>
<li>Secrets are stored securely in Key Vault and referenced in pipelines</li>
<li>Access controlled via Azure AD and RBAC</li>
<li>Automatic rotation and versioning of secrets</li>
<li>Audit logging of secret access</li>
</ul>
<pre><code># Creating a Key Vault-linked variable group
# In Azure DevOps UI: Pipelines > Library > Variable Groups > Link secrets from an Azure key vault

# Referencing in YAML pipeline
variables:
  - group: keyvault-secrets-group</code></pre>

<p><strong>2. Pipeline Variables marked as Secret</strong></p>
<ul>
<li>Define variables directly in the pipeline with "secret" flag</li>
<li>Values are masked in logs and not exposed to scripts by default</li>
<li>Good for project-specific secrets</li>
</ul>
<pre><code># In YAML pipeline
variables:
  - name: databasePassword
    value: $(DatabasePassword) # Value set in UI as secret

# In classic editor: mark variable as "Secret"</code></pre>

<p><strong>3. Secure Files</strong></p>
<ul>
<li>Upload certificates, SSH keys, and other sensitive files</li>
<li>Files are encrypted at rest and in transit</li>
<li>Downloaded temporarily during pipeline execution</li>
<li>Automatically cleaned up after use</li>
</ul>
<pre><code>steps:
- task: DownloadSecureFile@1
  name: sshKey
  inputs:
    secureFile: 'id_rsa'
- script: |
    chmod 700 $(sshKey.secureFilePath)
    ssh -i $(sshKey.secureFilePath) user@server</code></pre>

<p><strong>4. Service Connections</strong></p>
<ul>
<li>Store connection details for external services</li>
<li>Credentials are encrypted and not exposed in pipeline logs</li>
<li>Support for various authentication methods</li>
</ul>
<pre><code># Using a service connection in a deployment task
- task: AzureRmWebAppDeployment@4
  inputs:
    ConnectionType: 'AzureRM'
    azureSubscription: 'my-service-connection'
    appType: 'webApp'</code></pre>

<p><strong>5. Environment Variables</strong></p>
<ul>
<li>Set sensitive values as environment variables</li>
<li>Use system-managed environment variables where possible</li>
</ul>

<p><strong>Best practices we follow:</strong></p>
<ul>
<li><strong>Least privilege</strong>: Limit access to secrets to only those who need it</li>
<li><strong>No hardcoding</strong>: Never hardcode secrets in pipeline definitions or scripts</li>
<li><strong>Secret rotation</strong>: Regularly rotate secrets and credentials</li>
<li><strong>Audit access</strong>: Monitor and audit access to secrets</li>
<li><strong>Scope limitation</strong>: Use environment-specific secrets</li>
<li><strong>Avoid logging</strong>: Prevent secrets from appearing in logs</li>
<li><strong>Secret scanning</strong>: Implement scanning to detect accidentally committed secrets</li>
</ul>

<p>By combining these approaches, we maintain a secure pipeline environment while ensuring our automated processes have access to the credentials they need.</p>
</div>

### 26. How do you integrate Azure Key Vault to your Azure Pipelines? 🔑
<div class="answer">
<p>Integrating Azure Key Vault with Azure Pipelines provides a secure way to access secrets, certificates, and keys during pipeline execution. Here's how we implement this integration:</p>

<p><strong>Step 1: Set up Azure Key Vault</strong></p>
<ol>
<li>Create an Azure Key Vault in the Azure portal</li>
<li>Add your secrets, certificates, or keys to the vault</li>
<li>Set up access policies or RBAC permissions</li>
</ol>

<p><strong>Step 2: Create a service connection to Azure</strong></p>
<ol>
<li>In Azure DevOps, go to Project Settings > Service connections</li>
<li>Create a new Azure Resource Manager service connection</li>
<li>Ensure the service principal has at least "Get" and "List" permissions on the Key Vault</li>
</ol>

<p><strong>Step 3: Create a variable group linked to Key Vault</strong></p>
<ol>
<li>Go to Pipelines > Library > Variable groups</li>
<li>Create a new variable group</li>
<li>Enable "Link secrets from an Azure key vault as variables"</li>
<li>Select your Azure subscription and Key Vault</li>
<li>Choose which secrets to include in the variable group</li>
<li>Save the variable group</li>
</ol>

<p><strong>Step 4: Use the variable group in your pipeline</strong></p>
<p>In YAML pipeline:</p>
<pre><code>variables:
  - group: my-keyvault-variables

steps:
- script: |
    echo "Using secret: $(mySecret)"
  displayName: 'Use Key Vault secret'</code></pre>

<p>In classic editor:</p>
<ol>
<li>Edit your pipeline</li>
<li>Go to Variables tab</li>
<li>Select "Variable groups"</li>
<li>Link your Key Vault variable group</li>
</ol>

<p><strong>Step 5: Alternative - Direct Key Vault task</strong></p>
<p>For more dynamic access, use the Azure Key Vault task:</p>
<pre><code>steps:
- task: AzureKeyVault@2
  inputs:
    azureSubscription: 'my-azure-connection'
    KeyVaultName: 'my-keyvault'
    SecretsFilter: 'secret1,secret2'
    RunAsPreJob: true  # Makes secrets available to all subsequent tasks

- script: |
    echo "Using secret: $(secret1)"
  displayName: 'Use Key Vault secret'</code></pre>

<p><strong>Benefits of this approach:</strong></p>
<ul>
<li><strong>Centralized secret management</strong>: Secrets stored in one secure location</li>
<li><strong>Access control</strong>: Fine-grained control over who can access secrets</li>
<li><strong>Audit logging</strong>: All secret access is logged</li>
<li><strong>Secret rotation</strong>: Update secrets without changing pipeline code</li>
<li><strong>Compliance</strong>: Meets security and compliance requirements</li>
</ul>

<p><strong>Best practices we follow:</strong></p>
<ul>
<li>Use managed identities where possible instead of service principals</li>
<li>Apply the principle of least privilege for Key Vault access</li>
<li>Regularly rotate service principal credentials</li>
<li>Use different Key Vaults for different environments</li>
<li>Enable purge protection and soft delete on Key Vaults</li>
<li>Monitor and audit Key Vault access</li>
</ul>
</div>

### 27. Can you explain the CI/CD for Java application? ☕
<div class="answer">
<p>Setting up CI/CD for a Java application in Azure DevOps involves several specific considerations. Here's how we implement it:</p>

<p><strong>CI/CD Pipeline for Java Applications</strong></p>

<p><strong>1. Source Control Setup</strong></p>
<ul>
<li>Java project with Maven or Gradle build system</li>
<li>Git repository in Azure Repos or GitHub</li>
<li>Branch policies for main/develop branches</li>
<li>Pull request validation</li>
</ul>

<p><strong>2. Continuous Integration (Build Pipeline)</strong></p>
<p>YAML pipeline example:</p>
<pre><code>trigger:
  - main
  - develop

pool:
  vmImage: 'ubuntu-latest'

variables:
  MAVEN_CACHE_FOLDER: $(Pipeline.Workspace)/.m2/repository
  MAVEN_OPTS: '-Dmaven.repo.local=$(MAVEN_CACHE_FOLDER)'

steps:
- task: Cache@2
  inputs:
    key: 'maven | "$(Agent.OS)" | **/pom.xml'
    restoreKeys: |
      maven | "$(Agent.OS)"
    path: $(MAVEN_CACHE_FOLDER)
  displayName: 'Cache Maven packages'

- task: Maven@3
  inputs:
    mavenPomFile: 'pom.xml'
    goals: 'clean compile'
    options: $(MAVEN_OPTS)
  displayName: 'Compile Java code'

- task: Maven@3
  inputs:
    mavenPomFile: 'pom.xml'
    goals: 'test'
    options: $(MAVEN_OPTS)
  displayName: 'Run unit tests'

- task: SonarCloudPrepare@1
  inputs:
    SonarCloud: 'SonarCloud'
    organization: 'my-org'
    scannerMode: 'Other'
    extraProperties: |
      sonar.projectKey=my-project
      sonar.java.coveragePlugin=jacoco
      sonar.coverage.jacoco.xmlReportPaths=$(System.DefaultWorkingDirectory)/target/site/jacoco/jacoco.xml

- task: Maven@3
  inputs:
    mavenPomFile: 'pom.xml'
    goals: 'package sonar:sonar'
    options: $(MAVEN_OPTS)
  displayName: 'Package and analyze code'

- task: SonarCloudPublish@1
  inputs:
    pollingTimeoutSec: '300'

- task: Maven@3
  inputs:
    mavenPomFile: 'pom.xml'
    goals: 'verify'
    options: $(MAVEN_OPTS)
  displayName: 'Run integration tests'

- task: CopyFiles@2
  inputs:
    SourceFolder: 'target'
    Contents: '*.jar'
    TargetFolder: '$(Build.ArtifactStagingDirectory)'
  displayName: 'Copy JAR files'

- task: PublishBuildArtifacts@1
  inputs:
    PathtoPublish: '$(Build.ArtifactStagingDirectory)'
    ArtifactName: 'java-app'
  displayName: 'Publish artifacts'</code></pre>

<p><strong>3. Continuous Delivery (Release Pipeline)</strong></p>
<p>YAML deployment stages:</p>
<pre><code>stages:
- stage: Dev
  jobs:
  - deployment: DeployToDev
    environment: 'dev'
    strategy:
      runOnce:
        deploy:
          steps:
          - download: current
            artifact: 'java-app'
          - task: AzureWebApp@1
            inputs:
              azureSubscription: 'azure-service-connection'
              appType: 'webAppLinux'
              appName: 'my-java-app-dev'
              package: '$(Pipeline.Workspace)/java-app/*.jar'
              runtimeStack: 'JAVA|11'

- stage: Test
  dependsOn: Dev
  condition: succeeded()
  jobs:
  - deployment: DeployToTest
    environment: 'test'
    strategy:
      runOnce:
        deploy:
          steps:
          - download: current
            artifact: 'java-app'
          - task: AzureWebApp@1
            inputs:
              azureSubscription: 'azure-service-connection'
              appType: 'webAppLinux'
              appName: 'my-java-app-test'
              package: '$(Pipeline.Workspace)/java-app/*.jar'
              runtimeStack: 'JAVA|11'

- stage: Prod
  dependsOn: Test
  condition: succeeded()
  jobs:
  - deployment: DeployToProd
    environment: 'prod'
    strategy:
      runOnce:
        deploy:
          steps:
          - download: current
            artifact: 'java-app'
          - task: AzureWebApp@1
            inputs:
              azureSubscription: 'azure-service-connection'
              appType: 'webAppLinux'
              appName: 'my-java-app-prod'
              package: '$(Pipeline.Workspace)/java-app/*.jar'
              runtimeStack: 'JAVA|11'</code></pre>

<p><strong>4. Java-Specific Considerations</strong></p>
<ul>
<li><strong>Build tools</strong>: Maven or Gradle integration</li>
<li><strong>Testing frameworks</strong>: JUnit, TestNG, Mockito</li>
<li><strong>Code quality</strong>: SonarQube/SonarCloud for Java analysis</li>
<li><strong>Dependency scanning</strong>: OWASP dependency check</li>
<li><strong>Artifact repositories</strong>: Azure Artifacts or Nexus/Artifactory</li>
<li><strong>JVM versions</strong>: Multiple JDK support</li>
<li><strong>Spring Boot considerations</strong>: Actuator endpoints for health checks</li>
</ul>

<p><strong>5. Deployment Options for Java Applications</strong></p>
<ul>
<li><strong>Azure App Service</strong>: For web applications</li>
<li><strong>Azure Spring Cloud</strong>: For Spring Boot applications</li>
<li><strong>Azure Kubernetes Service</strong>: For containerized applications</li>
<li><strong>Azure Functions</strong>: For serverless Java applications</li>
<li><strong>Azure Virtual Machines</strong>: For custom deployment scenarios</li>
</ul>

<p><strong>6. Monitoring and Observability</strong></p>
<ul>
<li>Application Insights for Java</li>
<li>Log Analytics for centralized logging</li>
<li>JVM metrics collection</li>
<li>Custom health endpoints monitoring</li>
</ul>

<p>This CI/CD approach ensures our Java applications are thoroughly tested, analyzed for quality issues, and deployed consistently across environments.</p>
</div>

### 28. Can you explain the CI/CD for .NET application? 🔷
<div class="answer">
<p>Implementing CI/CD for a .NET application in Azure DevOps involves specific considerations for the .NET ecosystem. Here's our approach:</p>

<p><strong>CI/CD Pipeline for .NET Applications</strong></p>

<p><strong>1. Source Control Configuration</strong></p>
<ul>
<li>.NET solution with appropriate project structure</li>
<li>Git repository with branch policies</li>
<li>Solution and project files properly committed</li>
<li>.gitignore configured for .NET projects</li>
</ul>

<p><strong>2. Continuous Integration (Build Pipeline)</strong></p>
<p>YAML pipeline example:</p>
<pre><code>trigger:
  - main
  - develop

pool:
  vmImage: 'windows-latest'

variables:
  solution: '**/*.sln'
  buildPlatform: 'Any CPU'
  buildConfiguration: 'Release'

steps:
- task: NuGetToolInstaller@1
  displayName: 'Install NuGet tools'

- task: NuGetCommand@2
  inputs:
    restoreSolution: '$(solution)'
  displayName: 'Restore NuGet packages'

- task: DotNetCoreCLI@2
  inputs:
    command: 'restore'
    projects: '$(solution)'
  displayName: 'Restore .NET dependencies'

- task: VSBuild@1
  inputs:
    solution: '$(solution)'
    platform: '$(buildPlatform)'
    configuration: '$(buildConfiguration)'
  displayName: 'Build solution'

- task: DotNetCoreCLI@2
  inputs:
    command: 'test'
    projects: '**/*Tests/*.csproj'
    arguments: '--configuration $(buildConfiguration) --collect:"XPlat Code Coverage"'
  displayName: 'Run unit tests'

- task: PublishCodeCoverageResults@1
  inputs:
    codeCoverageTool: 'Cobertura'
    summaryFileLocation: '$(Agent.TempDirectory)/**/coverage.cobertura.xml'
  displayName: 'Publish code coverage'

- task: SonarCloudPrepare@1
  inputs:
    SonarCloud: 'SonarCloud'
    organization: 'my-org'
    scannerMode: 'MSBuild'
    projectKey: 'my-dotnet-project'
    projectName: 'My .NET Project'
    extraProperties: |
      sonar.cs.opencover.reportsPaths=$(Agent.TempDirectory)/**/coverage.opencover.xml

- task: SonarCloudAnalyze@1
  displayName: 'Run SonarCloud analysis'

- task: SonarCloudPublish@1
  inputs:
    pollingTimeoutSec: '300'
  displayName: 'Publish SonarCloud quality gate'

- task: DotNetCoreCLI@2
  inputs:
    command: 'publish'
    publishWebProjects: true
    arguments: '--configuration $(buildConfiguration) --output $(Build.ArtifactStagingDirectory)'
    zipAfterPublish: true
  displayName: 'Publish .NET application'

- task: PublishBuildArtifacts@1
  inputs:
    PathtoPublish: '$(Build.ArtifactStagingDirectory)'
    ArtifactName: 'dotnet-app'
  displayName: 'Publish artifacts'</code></pre>

<p><strong>3. Continuous Delivery (Release Pipeline)</strong></p>
<p>YAML deployment stages:</p>
<pre><code>stages:
- stage: Dev
  jobs:
  - deployment: DeployToDev
    environment: 'dev'
    strategy:
      runOnce:
        deploy:
          steps:
          - download: current
            artifact: 'dotnet-app'
          - task: AzureRmWebAppDeployment@4
            inputs:
              ConnectionType: 'AzureRM'
              azureSubscription: 'azure-service-connection'
              appType: 'webApp'
              WebAppName: 'my-dotnet-app-dev'
              packageForLinux: '$(Pipeline.Workspace)/dotnet-app/*.zip'
              enableCustomDeployment: true
              DeploymentType: 'webDeploy'
              RemoveAdditionalFilesFlag: true

- stage: Test
  dependsOn: Dev
  condition: succeeded()
  jobs:
  - deployment: DeployToTest
    environment: 'test'
    strategy:
      runOnce:
        deploy:
          steps:
          - download: current
            artifact: 'dotnet-app'
          - task: AzureRmWebAppDeployment@4
            inputs:
              ConnectionType: 'AzureRM'
              azureSubscription: 'azure-service-connection'
              appType: 'webApp'
              WebAppName: 'my-dotnet-app-test'
              packageForLinux: '$(Pipeline.Workspace)/dotnet-app/*.zip'
              enableCustomDeployment: true
              DeploymentType: 'webDeploy'
              RemoveAdditionalFilesFlag: true

- stage: Prod
  dependsOn: Test
  condition: succeeded()
  jobs:
  - deployment: DeployToProd
    environment: 'prod'
    strategy:
      runOnce:
        deploy:
          steps:
          - download: current
            artifact: 'dotnet-app'
          - task: AzureRmWebAppDeployment@4
            inputs:
              ConnectionType: 'AzureRM'
              azureSubscription: 'azure-service-connection'
              appType: 'webApp'
              WebAppName: 'my-dotnet-app-prod'
              packageForLinux: '$(Pipeline.Workspace)/dotnet-app/*.zip'
              enableCustomDeployment: true
              DeploymentType: 'webDeploy'
              RemoveAdditionalFilesFlag: true</code></pre>

<p><strong>4. .NET-Specific Considerations</strong></p>
<ul>
<li><strong>Framework versions</strong>: .NET Framework vs .NET Core/.NET 5+</li>
<li><strong>Testing frameworks</strong>: MSTest, NUnit, xUnit</li>
<li><strong>Code quality</strong>: StyleCop, FxCop, SonarQube</li>
<li><strong>Package management</strong>: NuGet packages and feeds</li>
<li><strong>Database migrations</strong>: Entity Framework migrations</li>
<li><strong>Configuration transformation</strong>: Web.config/appsettings.json transforms</li>
<li><strong>Assembly versioning</strong>: Automatic version numbering</li>
</ul>

<p><strong>5. Deployment Options for .NET Applications</strong></p>
<ul>
<li><strong>Azure App Service</strong>: For web applications</li>
<li><strong>Azure Functions</strong>: For serverless applications</li>
<li><strong>Azure Service Fabric</strong>: For microservices</li>
<li><strong>Azure Kubernetes Service</strong>: For containerized applications</li>
<li><strong>IIS on Azure VMs</strong>: For traditional .NET Framework applications</li>
</ul>

<p><strong>6. Application Monitoring</strong></p>
<ul>
<li>Application Insights integration</li>
<li>Health checks implementation</li>
<li>Custom telemetry</li>
<li>Performance monitoring</li>
</ul>

<p><strong>7. Database Deployment</strong></p>
<ul>
<li>DACPAC deployments for SQL Server</li>
<li>EF Core migrations</li>
<li>SQL scripts with SQLCMD</li>
</ul>

<p>This comprehensive approach ensures our .NET applications are built, tested, and deployed consistently and reliably across all environments.</p>
</div>

### 29. What are the common challenges that you have come across in Azure Pipeline? 🛠️
<div class="answer">
<p>Throughout my experience with Azure Pipelines, I've encountered and overcome several common challenges:</p>

<p><strong>1. Pipeline Performance Issues</strong></p>
<ul>
<li><strong>Challenge</strong>: Slow build and deployment times, especially for large projects</li>
<li><strong>Solution</strong>:
  <ul>
    <li>Implemented build caching for dependencies</li>
    <li>Parallelized test execution</li>
    <li>Used incremental builds where possible</li>
    <li>Optimized Docker image builds with layer caching</li>
    <li>Moved to self-hosted agents with better specifications for resource-intensive builds</li>
  </ul>
</li>
</ul>

<p><strong>2. Secret Management</strong></p>
<ul>
<li><strong>Challenge</strong>: Securely handling credentials and secrets across multiple environments</li>
<li><strong>Solution</strong>:
  <ul>
    <li>Integrated Azure Key Vault for centralized secret management</li>
    <li>Implemented just-in-time access for sensitive credentials</li>
    <li>Used variable groups with different scopes for different environments</li>
    <li>Added secret scanning in pre-commit hooks to prevent accidental commits</li>
  </ul>
</li>
</ul>

<p><strong>3. Environment Consistency</strong></p>
<ul>
<li><strong>Challenge</strong>: Ensuring consistent behavior across development, testing, and production environments</li>
<li><strong>Solution</strong>:
  <ul>
    <li>Adopted Infrastructure as Code (Terraform/ARM templates)</li>
    <li>Containerized applications to ensure consistency</li>
    <li>Implemented environment-specific configuration management</li>
    <li>Created validation stages to verify environment parity</li>
  </ul>
</li>
</ul>

<p><strong>4. Pipeline Complexity</strong></p>
<ul>
<li><strong>Challenge</strong>: Managing increasingly complex pipelines with multiple stages and dependencies</li>
<li><strong>Solution</strong>:
  <ul>
    <li>Refactored pipelines to use YAML templates for reusable components</li>
    <li>Implemented pipeline parameters for flexibility</li>
    <li>Created clear documentation for pipeline structure</li>
    <li>Used stage dependencies and conditions effectively</li>
  </ul>
</li>
</ul>

<p><strong>5. Flaky Tests</strong></p>
<ul>
<li><strong>Challenge</strong>: Intermittent test failures causing pipeline instability</li>
<li><strong>Solution</strong>:
  <ul>
    <li>Implemented test retry logic for transient failures</li>
    <li>Added detailed logging for test environments</li>
    <li>Isolated problematic tests and fixed root causes</li>
    <li>Created a separate pipeline for longer-running or less stable tests</li>
  </ul>
</li>
</ul>

<p><strong>6. Multi-Platform Support</strong></p>
<ul>
<li><strong>Challenge</strong>: Supporting builds and deployments across Windows, Linux, and macOS</li>
<li><strong>Solution</strong>:
  <ul>
    <li>Used matrix strategies to run jobs on multiple platforms</li>
    <li>Created platform-specific build steps with conditions</li>
    <li>Standardized scripts with cross-platform tools (PowerShell Core)</li>
    <li>Containerized build environments for consistency</li>
  </ul>
</li>
</ul>

<p><strong>7. Pipeline Permissions and Security</strong></p>
<ul>
<li><strong>Challenge</strong>: Managing access control and security for pipelines</li>
<li><strong>Solution</strong>:
  <ul>
    <li>Implemented pipeline resource protection</li>
    <li>Used service connections with minimal required permissions</li>
    <li>Added approval gates for production deployments</li>
    <li>Conducted regular security reviews of pipeline configurations</li>
  </ul>
</li>
</ul>

<p><strong>8. Dependency Management</strong></p>
<ul>
<li><strong>Challenge</strong>: Handling external dependencies and third-party services</li>
<li><strong>Solution</strong>:
  <ul>
    <li>Set up private artifact feeds</li>
    <li>Implemented dependency caching</li>
    <li>Created mock services for testing</li>
    <li>Added health checks for external services</li>
  </ul>
</li>
</ul>

<p>By systematically addressing these challenges, we've built more reliable, secure, and efficient CI/CD pipelines that support our development process effectively.</p>
</div>

### 30. Can you explain the Azure YAML pipeline structure? 📝
<div class="answer">
<p>Azure YAML pipelines follow a structured format that defines the entire CI/CD process as code. Here's a comprehensive explanation of the YAML pipeline structure:</p>

<p><strong>1. Top-Level Elements</strong></p>

<pre><code># Pipeline name
name: $(Date:yyyyMMdd)$(Rev:.r)

# Trigger definitions
trigger:
  branches:
    include:
    - main
    - releases/*
    exclude:
    - releases/old*
  paths:
    include:
    - src/*
    exclude:
    - docs/*

# PR trigger
pr:
  branches:
    include:
    - main
  paths:
    include:
    - src/*

# Scheduled triggers
schedules:
- cron: '0 0 * * *'
  displayName: 'Daily midnight build'
  branches:
    include:
    - main
  always: true

# Pipeline-level variables
variables:
  - name: projectName
    value: 'MyProject'
  - group: common-variables
  - template: variables/build-variables.yml

# Resources (repositories, pipelines, containers)
resources:
  repositories:
    - repository: templates
      type: git
      name: CommonTemplates
  pipelines:
    - pipeline: dependency
      source: DependencyPipeline
  containers:
    - container: linux
      image: ubuntu:latest

# Default pool for all jobs
pool:
  vmImage: 'ubuntu-latest'</code></pre>

<p><strong>2. Stages, Jobs, and Steps Structure</strong></p>

<pre><code>stages:
- stage: Build
  displayName: 'Build Stage'
  variables:
    buildConfiguration: 'Release'
  jobs:
  - job: Compile
    displayName: 'Compile and Test'
    steps:
    - script: echo "Building $(projectName)"
      displayName: 'Build project'
    
    - task: DotNetCoreCLI@2
      inputs:
        command: 'build'
        projects: '**/*.csproj'
        arguments: '--configuration $(buildConfiguration)'
      displayName: 'Build .NET projects'

- stage: Test
  dependsOn: Build
  condition: succeeded()
  jobs:
  - job: UnitTests
    displayName: 'Run Unit Tests'
    steps:
    - task: DotNetCoreCLI@2
      inputs:
        command: 'test'
        projects: '**/*Tests/*.csproj'
      displayName: 'Run tests'

  - job: IntegrationTests
    displayName: 'Run Integration Tests'
    steps:
    - script: echo "Running integration tests"</code></pre>

<p><strong>3. Deployment Jobs</strong></p>

<pre><code>- stage: Deploy
  dependsOn: Test
  condition: and(succeeded(), eq(variables['Build.SourceBranch'], 'refs/heads/main'))
  jobs:
  - deployment: DeployWebApp
    displayName: 'Deploy Web Application'
    environment: 'production'
    strategy:
      runOnce:
        deploy:
          steps:
          - task: AzureWebApp@1
            inputs:
              azureSubscription: 'production-subscription'
              appName: 'my-web-app'
              package: '$(Pipeline.Workspace)/drop/*.zip'</code></pre>

<p><strong>4. Templates and Reusable Components</strong></p>

<pre><code># Using a template
- template: templates/build-template.yml
  parameters:
    projectName: $(projectName)
    buildConfiguration: 'Release'</code></pre>

<p><strong>5. Key Structural Components</strong></p>
<ul>
<li><strong>Triggers</strong>: Define when the pipeline runs (branch changes, PRs, schedules)</li>
<li><strong>Variables</strong>: Define values used throughout the pipeline</li>
<li><strong>Resources</strong>: External resources used by the pipeline</li>
<li><strong>Stages</strong>: Major divisions in a pipeline (e.g., Build, Test, Deploy)</li>
<li><strong>Jobs</strong>: Groups of steps that run on the same agent</li>
<li><strong>Deployment Jobs</strong>: Specialized jobs for deploying to environments</li>
<li><strong>Steps</strong>: Individual actions (tasks, scripts, etc.)</li>
<li><strong>Templates</strong>: Reusable pipeline components</li>
</ul>

<p><strong>6. Advanced Features</strong></p>

<pre><code># Matrix strategy for multiple configurations
jobs:
- job: BuildMultiplePlatforms
  strategy:
    matrix:
      linux:
        imageName: 'ubuntu-latest'
        poolName: 'Linux'
      mac:
        imageName: 'macOS-latest'
        poolName: 'macOS'
      windows:
        imageName: 'windows-latest'
        poolName: 'Windows'
  pool:
    vmImage: $(imageName)
  steps:
  - script: echo "Building on $(imageName)"

# Conditional execution
steps:
- script: echo "This runs only on Windows"
  condition: eq(variables['Agent.OS'], 'Windows_NT')

# Output variables
steps:
- script: echo "##vso[task.setvariable variable=myOutputVar;isOutput=true]someValue"
  name: setvarStep
- script: echo $(setvarStep.myOutputVar)
  name: echovar</code></pre>

<p><strong>7. Best Practices We Follow</strong></p>
<ul>
<li>Organize complex pipelines into stages for better visualization</li>
<li>Use templates for common patterns to maintain DRY principle</li>
<li>Keep environment-specific configuration in variable groups</li>
<li>Use conditions to control execution flow</li>
<li>Add descriptive display names for better readability</li>
<li>Validate YAML with linters before committing</li>
<li>Use parameters for flexible, reusable pipelines</li>
</ul>

<p>This structured approach allows us to define complex build and release processes as code, enabling version control, review, and consistent execution.</p>
</div>

### 31. How do you enable the CI and CD for your Azure pipeline? 🔄
<div class="answer">
<p>Enabling CI (Continuous Integration) and CD (Continuous Delivery) in Azure Pipelines involves configuring triggers and deployment strategies. Here's how we implement both:</p>

<p><strong>Enabling Continuous Integration (CI)</strong></p>

<p><strong>1. Branch Triggers</strong></p>
<pre><code># Enable CI for specific branches
trigger:
  branches:
    include:
    - main
    - develop
    - feature/*
  paths:
    include:
    - src/*
    exclude:
    - docs/*
    - README.md</code></pre>

<p><strong>2. Pull Request Triggers</strong></p>
<pre><code># Enable CI for pull requests
pr:
  branches:
    include:
    - main
    - develop
  paths:
    include:
    - src/*
  drafts: false</code></pre>

<p><strong>3. Scheduled Triggers</strong></p>
<pre><code># Enable scheduled CI builds
schedules:
- cron: '0 2 * * *'
  displayName: 'Nightly build'
  branches:
    include:
    - main
  always: true</code></pre>

<p><strong>Enabling Continuous Delivery (CD)</strong></p>

<p><strong>1. Multi-Stage Pipeline with Deployment</strong></p>
<pre><code>stages:
- stage: Build
  jobs:
  - job: BuildJob
    steps:
    - script: echo "Building application"
    - task: PublishBuildArtifacts@1
      inputs:
        pathToPublish: '$(Build.ArtifactStagingDirectory)'
        artifactName: 'drop'

- stage: DeployDev
  dependsOn: Build
  condition: and(succeeded(), eq(variables['Build.SourceBranch'], 'refs/heads/develop'))
  jobs:
  - deployment: DeployToDev
    environment: 'development'
    strategy:
      runOnce:
        deploy:
          steps:
          - script: echo "Deploying to development"

- stage: DeployProd
  dependsOn: Build
  condition: and(succeeded(), eq(variables['Build.SourceBranch'], 'refs/heads/main'))
  jobs:
  - deployment: DeployToProd
    environment: 'production'
    strategy:
      runOnce:
        deploy:
          steps:
          - script: echo "Deploying to production"</code></pre>

<p><strong>2. Environment Configuration</strong></p>
<ul>
<li>Create environments in Azure DevOps (Pipelines > Environments)</li>
<li>Configure approval gates for production environments</li>
<li>Set up environment-specific variables</li>
<li>Configure deployment history and monitoring</li>
</ul>

<p><strong>3. Artifact Management</strong></p>
<pre><code># Publish artifacts in CI stage
- task: PublishBuildArtifacts@1
  inputs:
    pathToPublish: '$(Build.ArtifactStagingDirectory)'
    artifactName: 'webapp'

# Download artifacts in CD stage
- download: current
  artifact: 'webapp'</code></pre>

<p><strong>Best Practices for CI/CD Enablement:</strong></p>
<ul>
<li><strong>Branch Protection</strong>: Require successful builds before merging</li>
<li><strong>Quality Gates</strong>: Include code coverage and security scans</li>
<li><strong>Environment Promotion</strong>: Automatic deployment to dev, manual approval for production</li>
<li><strong>Rollback Strategy</strong>: Implement automated rollback on deployment failure</li>
<li><strong>Monitoring</strong>: Set up alerts for build and deployment failures</li>
</ul>
</div>

### 32. What are the best practices that you follow for Azure Pipelines? 🏆
<div class="answer">
<p>Based on our experience, here are the key best practices we follow for Azure Pipelines:</p>

<p><strong>1. Pipeline Structure and Organization</strong></p>
<ul>
<li><strong>Use YAML pipelines</strong>: Store pipeline definitions as code for version control</li>
<li><strong>Modular design</strong>: Break complex pipelines into reusable templates</li>
<li><strong>Clear naming conventions</strong>: Use descriptive names for stages, jobs, and steps</li>
<li><strong>Logical stage separation</strong>: Build → Test → Deploy with clear dependencies</li>
</ul>

<p><strong>2. Security Best Practices</strong></p>
<ul>
<li><strong>Secret management</strong>: Use Azure Key Vault integration for sensitive data</li>
<li><strong>Least privilege access</strong>: Grant minimal required permissions to service connections</li>
<li><strong>Environment protection</strong>: Implement approval gates for production deployments</li>
<li><strong>Secure variable groups</strong>: Mark sensitive variables as secrets</li>
<li><strong>Regular credential rotation</strong>: Rotate service principal credentials periodically</li>
</ul>

<p><strong>3. Performance Optimization</strong></p>
<ul>
<li><strong>Parallel execution</strong>: Run independent jobs in parallel</li>
<li><strong>Caching strategies</strong>: Cache dependencies and build outputs</li>
<li><strong>Incremental builds</strong>: Only build changed components when possible</li>
<li><strong>Appropriate agent selection</strong>: Choose right agent type for workload</li>
</ul>

<p><strong>4. Quality Assurance</strong></p>
<ul>
<li><strong>Automated testing</strong>: Include unit, integration, and functional tests</li>
<li><strong>Code quality gates</strong>: Integrate SonarQube or similar tools</li>
<li><strong>Security scanning</strong>: Include vulnerability scanning in pipelines</li>
<li><strong>Build validation</strong>: Validate builds on pull requests</li>
</ul>

<p><strong>5. Environment Management</strong></p>
<ul>
<li><strong>Environment parity</strong>: Keep environments as similar as possible</li>
<li><strong>Infrastructure as Code</strong>: Use Terraform/ARM templates for consistency</li>
<li><strong>Configuration management</strong>: Externalize configuration from code</li>
<li><strong>Blue-green deployments</strong>: Implement zero-downtime deployments</li>
</ul>

<p><strong>6. Monitoring and Observability</strong></p>
<ul>
<li><strong>Pipeline monitoring</strong>: Set up alerts for build failures</li>
<li><strong>Deployment tracking</strong>: Monitor deployment success rates</li>
<li><strong>Performance metrics</strong>: Track build times and success rates</li>
<li><strong>Log aggregation</strong>: Centralize logs for troubleshooting</li>
</ul>

<p><strong>7. Documentation and Maintenance</strong></p>
<ul>
<li><strong>Pipeline documentation</strong>: Document pipeline purpose and structure</li>
<li><strong>Runbook creation</strong>: Create troubleshooting guides</li>
<li><strong>Regular reviews</strong>: Periodically review and optimize pipelines</li>
<li><strong>Version control</strong>: Tag pipeline versions for releases</li>
</ul>

<p><strong>8. Error Handling and Recovery</strong></p>
<ul>
<li><strong>Retry logic</strong>: Implement retry for transient failures</li>
<li><strong>Graceful degradation</strong>: Handle partial failures appropriately</li>
<li><strong>Rollback procedures</strong>: Automate rollback on deployment failures</li>
<li><strong>Notification strategy</strong>: Alert relevant teams on failures</li>
</ul>

<p>These practices help us maintain reliable, secure, and efficient CI/CD pipelines that support our development and deployment processes effectively.</p>
</div>

### 33. How to create a self-hosted agent pool, explaining step by step? 🖥️
<div class="answer">
<p>Creating a self-hosted agent pool in Azure DevOps involves several steps. Here's a detailed walkthrough:</p>

<p><strong>Step 1: Create Agent Pool in Azure DevOps</strong></p>
<ol>
<li>Navigate to Azure DevOps organization settings</li>
<li>Go to "Agent pools" under "Pipelines"</li>
<li>Click "Add pool"</li>
<li>Select "Self-hosted" as pool type</li>
<li>Enter pool name (e.g., "MyCompany-Agents")</li>
<li>Set permissions and security settings</li>
<li>Click "Create"</li>
</ol>

<p><strong>Step 2: Prepare the Host Machine</strong></p>
<ul>
<li><strong>System Requirements</strong>:
  <ul>
    <li>Windows, Linux, or macOS</li>
    <li>Minimum 2 GB RAM, 4 GB recommended</li>
    <li>Network connectivity to Azure DevOps</li>
    <li>Required software for your builds (SDKs, tools, etc.)</li>
  </ul>
</li>
<li><strong>User Account</strong>:
  <ul>
    <li>Create a dedicated service account</li>
    <li>Grant necessary permissions for builds</li>
    <li>Ensure account can run as a service</li>
  </ul>
</li>
</ul>

<p><strong>Step 3: Download and Configure Agent</strong></p>
<ol>
<li>In the agent pool, click "New agent"</li>
<li>Select your operating system</li>
<li>Download the agent package</li>
<li>Extract to a directory (e.g., C:\agents\agent1)</li>
</ol>

<p><strong>Step 4: Configure the Agent (Windows)</strong></p>
<pre><code># Open PowerShell as Administrator
cd C:\agents\agent1

# Run configuration script
.\config.cmd

# Follow prompts:
# - Server URL: https://dev.azure.com/yourorganization
# - Authentication type: PAT (Personal Access Token)
# - Personal access token: [Enter your PAT]
# - Agent pool: [Select your pool]
# - Agent name: [Enter unique name]
# - Work folder: [Accept default or specify]
# - Run as service: Y
# - Service account: [Specify service account]</code></pre>

<p><strong>Step 5: Configure the Agent (Linux)</strong></p>
<pre><code># Extract and navigate to agent directory
cd ~/myagent

# Make script executable
chmod +x config.sh

# Run configuration
./config.sh

# Install as systemd service
sudo ./svc.sh install

# Start the service
sudo ./svc.sh start</code></pre>

<p><strong>Step 6: Create Personal Access Token (PAT)</strong></p>
<ol>
<li>Go to Azure DevOps user settings</li>
<li>Select "Personal access tokens"</li>
<li>Click "New Token"</li>
<li>Set appropriate scopes:
  <ul>
    <li>Agent Pools: Read & manage</li>
    <li>Build: Read & execute</li>
    <li>Release: Read, write, execute & manage</li>
  </ul>
</li>
<li>Copy the token for agent configuration</li>
</ol>

<p><strong>Step 7: Verify Agent Installation</strong></p>
<ol>
<li>Check agent status in Azure DevOps portal</li>
<li>Agent should appear as "Online" in the pool</li>
<li>Run a test pipeline to verify functionality</li>
</ol>

<p><strong>Step 8: Configure Agent Capabilities</strong></p>
<ul>
<li>Install required software (SDKs, tools, etc.)</li>
<li>Set environment variables</li>
<li>Configure system capabilities in Azure DevOps</li>
<li>Add custom capabilities if needed</li>
</ul>

<p><strong>Step 9: Security Configuration</strong></p>
<ul>
<li>Configure firewall rules for outbound HTTPS (443)</li>
<li>Set up network security groups if using Azure VMs</li>
<li>Configure antivirus exclusions for agent directories</li>
<li>Implement monitoring and logging</li>
</ul>

<p><strong>Step 10: Maintenance and Monitoring</strong></p>
<ul>
<li>Set up automated agent updates</li>
<li>Monitor agent health and performance</li>
<li>Configure log rotation</li>
<li>Set up alerts for agent offline status</li>
</ul>

<p><strong>Best Practices for Self-Hosted Agents:</strong></p>
<ul>
<li>Use dedicated machines for production agents</li>
<li>Implement proper backup and disaster recovery</li>
<li>Keep agents updated with latest versions</li>
<li>Use configuration management tools for consistency</li>
<li>Monitor resource usage and scale as needed</li>
<li>Implement proper security hardening</li>
</ul>

<p>This setup provides you with a reliable self-hosted agent that can access on-premises resources and provide consistent build environments.</p>
</div>

## GitHub Actions

### 34. What is the structure of GitHub Actions workflow? 🔧
<div class="answer">
<p>GitHub Actions workflows are defined using YAML files stored in the <code>.github/workflows</code> directory of your repository. Here's the complete structure:</p>

<p><strong>Basic Workflow Structure</strong></p>
<pre><code># Workflow name
name: CI/CD Pipeline

# Trigger events
on:
  push:
    branches: [ main, develop ]
    paths:
      - 'src/**'
      - '!docs/**'
  pull_request:
    branches: [ main ]
  schedule:
    - cron: '0 2 * * *'
  workflow_dispatch:
    inputs:
      environment:
        description: 'Environment to deploy'
        required: true
        default: 'dev'
        type: choice
        options:
        - dev
        - staging
        - prod

# Environment variables
env:
  NODE_VERSION: '18'
  REGISTRY: ghcr.io
  IMAGE_NAME: ${{ github.repository }}

# Default permissions
permissions:
  contents: read
  packages: write

# Jobs definition
jobs:
  build:
    name: Build Application
    runs-on: ubuntu-latest
    
    # Job-specific environment variables
    env:
      BUILD_CONFIG: Release
    
    # Job outputs
    outputs:
      version: ${{ steps.version.outputs.version }}
      artifact-name: ${{ steps.build.outputs.artifact-name }}
    
    # Job strategy for matrix builds
    strategy:
      matrix:
        os: [ubuntu-latest, windows-latest, macos-latest]
        node-version: [16, 18, 20]
      fail-fast: false
      max-parallel: 3
    
    # Steps within the job
    steps:
    - name: Checkout code
      uses: actions/checkout@v4
      with:
        fetch-depth: 0
    
    - name: Setup Node.js
      uses: actions/setup-node@v4
      with:
        node-version: ${{ matrix.node-version }}
        cache: 'npm'
    
    - name: Install dependencies
      run: npm ci
    
    - name: Run tests
      run: npm test
      env:
        CI: true
    
    - name: Build application
      id: build
      run: |
        npm run build
        echo "artifact-name=app-${{ github.sha }}" >> $GITHUB_OUTPUT
    
    - name: Upload artifacts
      uses: actions/upload-artifact@v4
      with:
        name: build-artifacts-${{ matrix.os }}
        path: dist/
        retention-days: 30

  deploy:
    name: Deploy to ${{ github.event.inputs.environment || 'dev' }}
    needs: build
    runs-on: ubuntu-latest
    environment: 
      name: ${{ github.event.inputs.environment || 'dev' }}
      url: https://myapp-${{ github.event.inputs.environment || 'dev' }}.example.com
    
    steps:
    - name: Download artifacts
      uses: actions/download-artifact@v4
      with:
        name: build-artifacts-ubuntu-latest
        path: ./dist
    
    - name: Deploy to environment
      run: echo "Deploying to ${{ github.event.inputs.environment || 'dev' }}"</code></pre>

<p><strong>Key Components Explained:</strong></p>

<p><strong>1. Workflow Triggers (on)</strong></p>
<ul>
<li><strong>push</strong>: Triggered on code push to specified branches</li>
<li><strong>pull_request</strong>: Triggered on PR creation/updates</li>
<li><strong>schedule</strong>: Cron-based scheduling</li>
<li><strong>workflow_dispatch</strong>: Manual trigger with inputs</li>
<li><strong>release</strong>: Triggered on release events</li>
<li><strong>issues</strong>: Triggered on issue events</li>
</ul>

<p><strong>2. Jobs Structure</strong></p>
<ul>
<li><strong>runs-on</strong>: Specifies the runner environment</li>
<li><strong>needs</strong>: Defines job dependencies</li>
<li><strong>if</strong>: Conditional job execution</li>
<li><strong>strategy</strong>: Matrix builds for multiple configurations</li>
<li><strong>environment</strong>: Deployment environment settings</li>
</ul>

<p><strong>3. Steps Structure</strong></p>
<ul>
<li><strong>name</strong>: Human-readable step description</li>
<li><strong>uses</strong>: References a pre-built action</li>
<li><strong>run</strong>: Executes shell commands</li>
<li><strong>with</strong>: Provides inputs to actions</li>
<li><strong>env</strong>: Sets environment variables for the step</li>
<li><strong>if</strong>: Conditional step execution</li>
<li><strong>id</strong>: Unique identifier for referencing step outputs</li>
</ul>

<p><strong>4. Advanced Features</strong></p>

<p><strong>Reusable Workflows:</strong></p>
<pre><code># .github/workflows/reusable-workflow.yml
on:
  workflow_call:
    inputs:
      environment:
        required: true
        type: string
    secrets:
      token:
        required: true

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
    - name: Deploy
      run: echo "Deploying to ${{ inputs.environment }}"</code></pre>

<p><strong>Composite Actions:</strong></p>
<pre><code># .github/actions/setup-app/action.yml
name: 'Setup Application'
description: 'Setup Node.js and install dependencies'
inputs:
  node-version:
    description: 'Node.js version'
    required: false
    default: '18'
runs:
  using: 'composite'
  steps:
  - uses: actions/setup-node@v4
    with:
      node-version: ${{ inputs.node-version }}
  - run: npm ci
    shell: bash</code></pre>

<p>This structure provides a comprehensive framework for defining complex CI/CD workflows with GitHub Actions.</p>
</div>

### 35. What is the difference between GitHub hosted vs GitHub self-hosted runners? 🏃‍♂️
<div class="answer">
<p>GitHub provides two types of runners for executing workflows: GitHub-hosted and self-hosted runners. Each has distinct characteristics:</p>

<p><strong>GitHub-Hosted Runners</strong></p>
<ul>
<li><strong>Management</strong>: Fully managed by GitHub</li>
<li><strong>Environment</strong>: Fresh virtual machine for each job</li>
<li><strong>Operating Systems</strong>: Ubuntu, Windows, and macOS available</li>
<li><strong>Pre-installed Software</strong>: Comprehensive set of tools and SDKs</li>
<li><strong>Specifications</strong>:
  <ul>
    <li>2-core CPU</li>
    <li>7 GB RAM</li>
    <li>14 GB SSD storage</li>
  </ul>
</li>
<li><strong>Network</strong>: Public internet access</li>
<li><strong>Cost</strong>: Included minutes with GitHub plans, pay for additional usage</li>
<li><strong>Maintenance</strong>: Zero maintenance required</li>
<li><strong>Scalability</strong>: Automatic scaling based on demand</li>
<li><strong>Security</strong>: Isolated environment for each run</li>
</ul>

<p><strong>Self-Hosted Runners</strong></p>
<ul>
<li><strong>Management</strong>: You provision and maintain the infrastructure</li>
<li><strong>Environment</strong>: Persistent between runs (unless configured otherwise)</li>
<li><strong>Operating Systems</strong>: Any OS that supports the runner application</li>
<li><strong>Software</strong>: Complete control over installed tools and versions</li>
<li><strong>Specifications</strong>: Customizable based on your hardware</li>
<li><strong>Network</strong>: Can access private networks and on-premises resources</li>
<li><strong>Cost</strong>: You pay for infrastructure, but runner minutes are free</li>
<li><strong>Maintenance</strong>: You handle updates, security, and maintenance</li>
<li><strong>Scalability</strong>: Manual scaling or custom auto-scaling solutions</li>
<li><strong>Security</strong>: You control the security configuration</li>
</ul>

<p><strong>Comparison Table</strong></p>
<table>
<tr>
<th>Aspect</th>
<th>GitHub-Hosted</th>
<th>Self-Hosted</th>
</tr>
<tr>
<td>Setup Time</td>
<td>Immediate</td>
<td>Requires setup and configuration</td>
</tr>
<tr>
<td>Maintenance</td>
<td>None</td>
<td>Regular updates and maintenance</td>
</tr>
<tr>
<td>Customization</td>
<td>Limited</td>
<td>Full control</td>
</tr>
<tr>
<td>Performance</td>
<td>Fixed specifications</td>
<td>Customizable performance</td>
</tr>
<tr>
<td>Network Access</td>
<td>Public internet only</td>
<td>Private networks accessible</td>
</tr>
<tr>
<td>Security</td>
<td>Managed by GitHub</td>
<td>Your responsibility</td>
</tr>
<tr>
<td>Cost Model</td>
<td>Pay per minute</td>
<td>Infrastructure cost only</td>
</tr>
</table>

<p><strong>When to Use GitHub-Hosted Runners:</strong></p>
<ul>
<li>Standard build and test scenarios</li>
<li>Open source projects</li>
<li>Teams wanting minimal maintenance overhead</li>
<li>Projects with standard tooling requirements</li>
<li>Occasional or low-volume builds</li>
</ul>

<p><strong>When to Use Self-Hosted Runners:</strong></p>
<ul>
<li>Need access to on-premises resources</li>
<li>Require specific hardware or software configurations</li>
<li>High-volume builds (cost optimization)</li>
<li>Need more powerful hardware than GitHub provides</li>
<li>Compliance requirements for data locality</li>
<li>Custom security requirements</li>
<li>Long-running jobs (GitHub-hosted has 6-hour limit)</li>
</ul>

<p><strong>Security Considerations:</strong></p>
<ul>
<li><strong>GitHub-Hosted</strong>: Isolated, ephemeral environments</li>
<li><strong>Self-Hosted</strong>: Persistent environments require careful security management</li>
<li>Never use self-hosted runners for public repositories due to security risks</li>
<li>Implement proper access controls and monitoring for self-hosted runners</li>
</ul>

<p>In our organization, we use GitHub-hosted runners for standard CI tasks and self-hosted runners for deployments requiring access to our internal infrastructure.</p>
</div>

### 36. Can you explain step by step how do you deploy Terraform using GitHub Actions? 🏗️
<div class="answer">
<p>Deploying Terraform infrastructure using GitHub Actions requires careful setup and security considerations. Here's a comprehensive step-by-step approach:</p>

<p><strong>Step 1: Repository Structure Setup</strong></p>
<pre><code>my-terraform-project/
├── .github/
│   └── workflows/
│       └── terraform.yml
├── terraform/
│   ├── main.tf
│   ├── variables.tf
│   ├── outputs.tf
│   └── terraform.tfvars.example
└── README.md</code></pre>

<p><strong>Step 2: Configure Azure Service Principal</strong></p>
<pre><code># Create service principal
az ad sp create-for-rbac --name "terraform-github-actions" \
  --role="Contributor" \
  --scopes="/subscriptions/YOUR_SUBSCRIPTION_ID" \
  --sdk-auth

# Output will be JSON - save this for GitHub secrets</code></pre>

<p><strong>Step 3: Set up GitHub Secrets</strong></p>
<p>In your GitHub repository, go to Settings > Secrets and variables > Actions, and add:</p>
<ul>
<li><code>AZURE_CREDENTIALS</code>: The JSON output from service principal creation</li>
<li><code>ARM_CLIENT_ID</code>: Service principal client ID</li>
<li><code>ARM_CLIENT_SECRET</code>: Service principal client secret</li>
<li><code>ARM_SUBSCRIPTION_ID</code>: Azure subscription ID</li>
<li><code>ARM_TENANT_ID</code>: Azure tenant ID</li>
<li><code>TF_STATE_STORAGE_ACCOUNT</code>: Storage account for Terraform state</li>
<li><code>TF_STATE_CONTAINER</code>: Container name for state files</li>
</ul>

<p><strong>Step 4: Create Terraform Backend Configuration</strong></p>
<pre><code># terraform/backend.tf
terraform {
  backend "azurerm" {
    resource_group_name  = "terraform-state-rg"
    storage_account_name = "tfstate12345"
    container_name       = "tfstate"
    key                  = "terraform.tfstate"
  }
}</code></pre>

<p><strong>Step 5: Create GitHub Actions Workflow</strong></p>
<pre><code># .github/workflows/terraform.yml
name: 'Terraform CI/CD'

on:
  push:
    branches:
      - main
      - develop
    paths:
      - 'terraform/**'
  pull_request:
    branches:
      - main
    paths:
      - 'terraform/**'
  workflow_dispatch:
    inputs:
      action:
        description: 'Terraform action to perform'
        required: true
        default: 'plan'
        type: choice
        options:
        - plan
        - apply
        - destroy

env:
  TF_VERSION: '1.5.0'
  TF_WORKING_DIR: './terraform'

jobs:
  terraform-check:
    name: 'Terraform Check'
    runs-on: ubuntu-latest
    if: github.event_name == 'pull_request'
    
    steps:
    - name: Checkout
      uses: actions/checkout@v4

    - name: Setup Terraform
      uses: hashicorp/setup-terraform@v3
      with:
        terraform_version: ${{ env.TF_VERSION }}

    - name: Terraform Format Check
      working-directory: ${{ env.TF_WORKING_DIR }}
      run: terraform fmt -check -recursive

    - name: Terraform Init
      working-directory: ${{ env.TF_WORKING_DIR }}
      env:
        ARM_CLIENT_ID: ${{ secrets.ARM_CLIENT_ID }}
        ARM_CLIENT_SECRET: ${{ secrets.ARM_CLIENT_SECRET }}
        ARM_SUBSCRIPTION_ID: ${{ secrets.ARM_SUBSCRIPTION_ID }}
        ARM_TENANT_ID: ${{ secrets.ARM_TENANT_ID }}
      run: |
        terraform init \
          -backend-config="storage_account_name=${{ secrets.TF_STATE_STORAGE_ACCOUNT }}" \
          -backend-config="container_name=${{ secrets.TF_STATE_CONTAINER }}"

    - name: Terraform Validate
      working-directory: ${{ env.TF_WORKING_DIR }}
      run: terraform validate

    - name: Terraform Plan
      working-directory: ${{ env.TF_WORKING_DIR }}
      env:
        ARM_CLIENT_ID: ${{ secrets.ARM_CLIENT_ID }}
        ARM_CLIENT_SECRET: ${{ secrets.ARM_CLIENT_SECRET }}
        ARM_SUBSCRIPTION_ID: ${{ secrets.ARM_SUBSCRIPTION_ID }}
        ARM_TENANT_ID: ${{ secrets.ARM_TENANT_ID }}
      run: terraform plan -no-color

  terraform-plan:
    name: 'Terraform Plan'
    runs-on: ubuntu-latest
    if: github.ref == 'refs/heads/develop' || github.event_name == 'workflow_dispatch'
    
    outputs:
      tfplanExitCode: ${{ steps.tf-plan.outputs.exitcode }}
    
    steps:
    - name: Checkout
      uses: actions/checkout@v4

    - name: Setup Terraform
      uses: hashicorp/setup-terraform@v3
      with:
        terraform_version: ${{ env.TF_VERSION }}

    - name: Terraform Init
      working-directory: ${{ env.TF_WORKING_DIR }}
      env:
        ARM_CLIENT_ID: ${{ secrets.ARM_CLIENT_ID }}
        ARM_CLIENT_SECRET: ${{ secrets.ARM_CLIENT_SECRET }}
        ARM_SUBSCRIPTION_ID: ${{ secrets.ARM_SUBSCRIPTION_ID }}
        ARM_TENANT_ID: ${{ secrets.ARM_TENANT_ID }}
      run: |
        terraform init \
          -backend-config="storage_account_name=${{ secrets.TF_STATE_STORAGE_ACCOUNT }}" \
          -backend-config="container_name=${{ secrets.TF_STATE_CONTAINER }}"

    - name: Terraform Plan
      id: tf-plan
      working-directory: ${{ env.TF_WORKING_DIR }}
      env:
        ARM_CLIENT_ID: ${{ secrets.ARM_CLIENT_ID }}
        ARM_CLIENT_SECRET: ${{ secrets.ARM_CLIENT_SECRET }}
        ARM_SUBSCRIPTION_ID: ${{ secrets.ARM_SUBSCRIPTION_ID }}
        ARM_TENANT_ID: ${{ secrets.ARM_TENANT_ID }}
      run: |
        export exitcode=0
        terraform plan -detailed-exitcode -no-color -out tfplan || export exitcode=$?
        
        echo "exitcode=$exitcode" >> $GITHUB_OUTPUT
        
        if [ $exitcode -eq 1 ]; then
          echo "Terraform Plan Failed"
          exit 1
        elif [ $exitcode -eq 2 ]; then
          echo "Terraform Plan Succeeded with Changes"
        else
          echo "Terraform Plan Succeeded with No Changes"
        fi

    - name: Publish Terraform Plan
      uses: actions/upload-artifact@v4
      with:
        name: tfplan
        path: ${{ env.TF_WORKING_DIR }}/tfplan

  terraform-apply:
    name: 'Terraform Apply'
    runs-on: ubuntu-latest
    needs: [terraform-plan]
    if: |
      github.ref == 'refs/heads/main' && 
      needs.terraform-plan.outputs.tfplanExitCode == 2 ||
      github.event.inputs.action == 'apply'
    environment: production
    
    steps:
    - name: Checkout
      uses: actions/checkout@v4

    - name: Setup Terraform
      uses: hashicorp/setup-terraform@v3
      with:
        terraform_version: ${{ env.TF_VERSION }}

    - name: Terraform Init
      working-directory: ${{ env.TF_WORKING_DIR }}
      env:
        ARM_CLIENT_ID: ${{ secrets.ARM_CLIENT_ID }}
        ARM_CLIENT_SECRET: ${{ secrets.ARM_CLIENT_SECRET }}
        ARM_SUBSCRIPTION_ID: ${{ secrets.ARM_SUBSCRIPTION_ID }}
        ARM_TENANT_ID: ${{ secrets.ARM_TENANT_ID }}
      run: |
        terraform init \
          -backend-config="storage_account_name=${{ secrets.TF_STATE_STORAGE_ACCOUNT }}" \
          -backend-config="container_name=${{ secrets.TF_STATE_CONTAINER }}"

    - name: Download Terraform Plan
      uses: actions/download-artifact@v4
      with:
        name: tfplan
        path: ${{ env.TF_WORKING_DIR }}

    - name: Terraform Apply
      working-directory: ${{ env.TF_WORKING_DIR }}
      env:
        ARM_CLIENT_ID: ${{ secrets.ARM_CLIENT_ID }}
        ARM_CLIENT_SECRET: ${{ secrets.ARM_CLIENT_SECRET }}
        ARM_SUBSCRIPTION_ID: ${{ secrets.ARM_SUBSCRIPTION_ID }}
        ARM_TENANT_ID: ${{ secrets.ARM_TENANT_ID }}
      run: terraform apply -auto-approve tfplan</code></pre>

<p><strong>Step 6: Set up Environment Protection</strong></p>
<ol>
<li>Go to repository Settings > Environments</li>
<li>Create "production" environment</li>
<li>Add required reviewers for approval</li>
<li>Set deployment branch rules</li>
</ol>

<p><strong>Step 7: Best Practices Implementation</strong></p>
<ul>
<li><strong>State file security</strong>: Use encrypted storage with access controls</li>
<li><strong>Plan artifacts</strong>: Save and reuse plan files between jobs</li>
<li><strong>Environment separation</strong>: Use different state files for different environments</li>
<li><strong>Approval gates</strong>: Require manual approval for production deployments</li>
<li><strong>Drift detection</strong>: Regular scheduled runs to detect configuration drift</li>
</ul>

<p>This workflow provides a secure, automated way to deploy Terraform infrastructure with proper validation, planning, and approval processes.</p>
</div>

### 37. Can you explain step by step how do you deploy a Java application using GitHub Actions? ☕
<div class="answer">
<p>Deploying a Java application using GitHub Actions involves building, testing, and deploying the application. Here's a comprehensive step-by-step approach:</p>

<p><strong>Step 1: Repository Structure</strong></p>
<pre><code>java-app/
├── .github/
│   └── workflows/
│       └── ci-cd.yml
├── src/
│   ├── main/
│   │   └── java/
│   └── test/
│       └── java/
├── pom.xml (for Maven) or build.gradle (for Gradle)
├── Dockerfile
└── README.md</code></pre>

<p><strong>Step 2: Create GitHub Actions Workflow</strong></p>
<pre><code># .github/workflows/ci-cd.yml
name: Java CI/CD Pipeline

on:
  push:
    branches: [ main, develop ]
  pull_request:
    branches: [ main ]
  workflow_dispatch:

env:
  JAVA_VERSION: '17'
  MAVEN_OPTS: '-Xmx1024m'
  REGISTRY: ghcr.io
  IMAGE_NAME: ${{ github.repository }}

jobs:
  test:
    name: Test Application
    runs-on: ubuntu-latest
    
    steps:
    - name: Checkout code
      uses: actions/checkout@v4

    - name: Set up JDK ${{ env.JAVA_VERSION }}
      uses: actions/setup-java@v4
      with:
        java-version: ${{ env.JAVA_VERSION }}
        distribution: 'temurin'
        cache: maven

    - name: Run tests
      run: mvn clean test

    - name: Generate test report
      uses: dorny/test-reporter@v1
      if: success() || failure()
      with:
        name: Maven Tests
        path: target/surefire-reports/*.xml
        reporter: java-junit

    - name: Upload test results
      uses: actions/upload-artifact@v4
      if: always()
      with:
        name: test-results
        path: target/surefire-reports/

  build:
    name: Build Application
    runs-on: ubuntu-latest
    needs: test
    
    outputs:
      version: ${{ steps.version.outputs.version }}
      image-digest: ${{ steps.build.outputs.digest }}
    
    steps:
    - name: Checkout code
      uses: actions/checkout@v4

    - name: Set up JDK ${{ env.JAVA_VERSION }}
      uses: actions/setup-java@v4
      with:
        java-version: ${{ env.JAVA_VERSION }}
        distribution: 'temurin'
        cache: maven

    - name: Get version
      id: version
      run: |
        VERSION=$(mvn help:evaluate -Dexpression=project.version -q -DforceStdout)
        echo "version=$VERSION" >> $GITHUB_OUTPUT
        echo "Version: $VERSION"

    - name: Build application
      run: mvn clean compile package -DskipTests

    - name: Upload JAR artifact
      uses: actions/upload-artifact@v4
      with:
        name: java-app-${{ steps.version.outputs.version }}
        path: target/*.jar

    - name: Set up Docker Buildx
      uses: docker/setup-buildx-action@v3

    - name: Log in to Container Registry
      uses: docker/login-action@v3
      with:
        registry: ${{ env.REGISTRY }}
        username: ${{ github.actor }}
        password: ${{ secrets.GITHUB_TOKEN }}

    - name: Extract metadata
      id: meta
      uses: docker/metadata-action@v5
      with:
        images: ${{ env.REGISTRY }}/${{ env.IMAGE_NAME }}
        tags: |
          type=ref,event=branch
          type=ref,event=pr
          type=semver,pattern={{version}}
          type=sha,prefix={{branch}}-

    - name: Build and push Docker image
      id: build
      uses: docker/build-push-action@v5
      with:
        context: .
        push: true
        tags: ${{ steps.meta.outputs.tags }}
        labels: ${{ steps.meta.outputs.labels }}
        cache-from: type=gha
        cache-to: type=gha,mode=max

  security-scan:
    name: Security Scan
    runs-on: ubuntu-latest
    needs: build
    
    steps:
    - name: Checkout code
      uses: actions/checkout@v4

    - name: Run Trivy vulnerability scanner
      uses: aquasecurity/trivy-action@master
      with:
        image-ref: ${{ env.REGISTRY }}/${{ env.IMAGE_NAME }}:${{ github.sha }}
        format: 'sarif'
        output: 'trivy-results.sarif'

    - name: Upload Trivy scan results
      uses: github/codeql-action/upload-sarif@v3
      with:
        sarif_file: 'trivy-results.sarif'

  deploy-dev:
    name: Deploy to Development
    runs-on: ubuntu-latest
    needs: [build, security-scan]
    if: github.ref == 'refs/heads/develop'
    environment: development
    
    steps:
    - name: Deploy to Azure App Service
      uses: azure/webapps-deploy@v2
      with:
        app-name: 'java-app-dev'
        publish-profile: ${{ secrets.AZURE_WEBAPP_PUBLISH_PROFILE_DEV }}
        images: ${{ env.REGISTRY }}/${{ env.IMAGE_NAME }}:${{ github.sha }}

  deploy-staging:
    name: Deploy to Staging
    runs-on: ubuntu-latest
    needs: [build, security-scan]
    if: github.ref == 'refs/heads/main'
    environment: staging
    
    steps:
    - name: Deploy to Azure App Service
      uses: azure/webapps-deploy@v2
      with:
        app-name: 'java-app-staging'
        publish-profile: ${{ secrets.AZURE_WEBAPP_PUBLISH_PROFILE_STAGING }}
        images: ${{ env.REGISTRY }}/${{ env.IMAGE_NAME }}:${{ github.sha }}

  deploy-production:
    name: Deploy to Production
    runs-on: ubuntu-latest
    needs: [deploy-staging]
    if: github.ref == 'refs/heads/main'
    environment: production
    
    steps:
    - name: Deploy to Azure App Service
      uses: azure/webapps-deploy@v2
      with:
        app-name: 'java-app-prod'
        publish-profile: ${{ secrets.AZURE_WEBAPP_PUBLISH_PROFILE_PROD }}
        images: ${{ env.REGISTRY }}/${{ env.IMAGE_NAME }}:${{ github.sha }}

    - name: Run smoke tests
      run: |
        sleep 30
        curl -f https://java-app-prod.azurewebsites.net/health || exit 1</code></pre>

<p><strong>Step 3: Create Dockerfile</strong></p>
<pre><code># Dockerfile
FROM openjdk:17-jre-slim

WORKDIR /app

COPY target/*.jar app.jar

EXPOSE 8080

HEALTHCHECK --interval=30s --timeout=3s --start-period=5s --retries=3 \
  CMD curl -f http://localhost:8080/actuator/health || exit 1

ENTRYPOINT ["java", "-jar", "app.jar"]</code></pre>

<p><strong>Step 4: Configure GitHub Secrets</strong></p>
<ul>
<li><code>AZURE_WEBAPP_PUBLISH_PROFILE_DEV</code></li>
<li><code>AZURE_WEBAPP_PUBLISH_PROFILE_STAGING</code></li>
<li><code>AZURE_WEBAPP_PUBLISH_PROFILE_PROD</code></li>
<li><code>SONAR_TOKEN</code> (if using SonarCloud)</li>
</ul>

<p><strong>Step 5: Set up Environments</strong></p>
<ol>
<li>Go to repository Settings > Environments</li>
<li>Create environments: development, staging, production</li>
<li>Configure protection rules and required reviewers</li>
<li>Set environment-specific secrets</li>
</ol>

<p>This workflow provides comprehensive CI/CD for Java applications with testing, security scanning, and multi-environment deployment.</p>
</div>

### 38. How do you maintain the secrets in GitHub Actions workflow? 🔐
<div class="answer">
<p>Managing secrets securely in GitHub Actions is crucial for protecting sensitive information. Here are the methods and best practices we use:</p>

<p><strong>1. Repository Secrets</strong></p>
<ul>
<li>Stored at the repository level</li>
<li>Accessible to all workflows in the repository</li>
<li>Encrypted at rest and in transit</li>
<li>Not exposed in logs or to forked repositories</li>
</ul>

<p><strong>Setting up repository secrets:</strong></p>
<ol>
<li>Go to repository Settings > Secrets and variables > Actions</li>
<li>Click "New repository secret"</li>
<li>Add name and value</li>
<li>Use in workflows with <code>${{ secrets.SECRET_NAME }}</code></li>
</ol>

<p><strong>2. Environment Secrets</strong></p>
<ul>
<li>Scoped to specific environments</li>
<li>Provide additional security with approval gates</li>
<li>Override repository secrets with same name</li>
</ul>

<pre><code># Using environment secrets
jobs:
  deploy:
    runs-on: ubuntu-latest
    environment: production
    steps:
    - name: Deploy
      env:
        API_KEY: ${{ secrets.PROD_API_KEY }}
      run: echo "Deploying with production API key"</code></pre>

<p><strong>3. Organization Secrets</strong></p>
<ul>
<li>Shared across multiple repositories in an organization</li>
<li>Useful for common credentials like registry access</li>
<li>Can be restricted to specific repositories</li>
</ul>

<p><strong>4. Azure Key Vault Integration</strong></p>
<pre><code>jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
    - name: Login to Azure
      uses: azure/login@v1
      with:
        creds: ${{ secrets.AZURE_CREDENTIALS }}
    
    - name: Get secrets from Key Vault
      uses: azure/get-keyvault-secrets@v1
      with:
        keyvault: "my-key-vault"
        secrets: 'database-password, api-key'
      id: keyvault
    
    - name: Use secrets
      env:
        DB_PASSWORD: ${{ steps.keyvault.outputs.database-password }}
        API_KEY: ${{ steps.keyvault.outputs.api-key }}
      run: |
        echo "Using secrets from Key Vault"</code></pre>

<p><strong>5. HashiCorp Vault Integration</strong></p>
<pre><code>jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
    - name: Import Secrets from Vault
      uses: hashicorp/vault-action@v2
      with:
        url: https://vault.example.com:8200
        token: ${{ secrets.VAULT_TOKEN }}
        secrets: |
          secret/data/prod database_password | DATABASE_PASSWORD ;
          secret/data/prod api_key | API_KEY
    
    - name: Use secrets
      env:
        DB_PASSWORD: ${{ env.DATABASE_PASSWORD }}
        API_KEY: ${{ env.API_KEY }}
      run: echo "Using secrets from Vault"</code></pre>

<p><strong>6. AWS Secrets Manager Integration</strong></p>
<pre><code>jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
    - name: Configure AWS credentials
      uses: aws-actions/configure-aws-credentials@v4
      with:
        aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
        aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
        aws-region: us-east-1
    
    - name: Get secrets from AWS Secrets Manager
      uses: aws-actions/aws-secretsmanager-get-secrets@v1
      with:
        secret-ids: |
          prod/database
          prod/api-keys
        parse-json-secrets: true
    
    - name: Use secrets
      env:
        DB_PASSWORD: ${{ env.PROD_DATABASE_PASSWORD }}
        API_KEY: ${{ env.PROD_API_KEYS_API_KEY }}
      run: echo "Using secrets from AWS"</code></pre>

<p><strong>7. Best Practices for Secret Management</strong></p>

<p><strong>Security Best Practices:</strong></p>
<ul>
<li><strong>Principle of least privilege</strong>: Only grant access to secrets that are needed</li>
<li><strong>Environment separation</strong>: Use different secrets for different environments</li>
<li><strong>Regular rotation</strong>: Rotate secrets regularly</li>
<li><strong>Audit access</strong>: Monitor who accesses secrets and when</li>
<li><strong>No hardcoding</strong>: Never hardcode secrets in workflow files</li>
</ul>

<p><strong>Workflow Best Practices:</strong></p>
<pre><code># Good: Using secrets properly
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
    - name: Deploy application
      env:
        API_KEY: ${{ secrets.API_KEY }}
        DB_PASSWORD: ${{ secrets.DB_PASSWORD }}
      run: |
        # Secrets are available as environment variables
        ./deploy.sh

# Bad: Exposing secrets in logs
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
    - name: Debug (DON'T DO THIS)
      run: echo "API Key is ${{ secrets.API_KEY }}"</code></pre>

<p><strong>8. Secret Scanning and Prevention</strong></p>
<ul>
<li>Enable GitHub's secret scanning</li>
<li>Use pre-commit hooks to prevent secret commits</li>
<li>Implement secret detection in CI/CD pipelines</li>
<li>Use tools like GitLeaks or TruffleHog</li>
</ul>

<p><strong>9. Dynamic Secret Generation</strong></p>
<pre><code>jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
    - name: Generate temporary credentials
      id: temp-creds
      run: |
        # Generate temporary token
        TOKEN=$(curl -X POST "https://api.example.com/auth" \
          -H "Authorization: Bearer ${{ secrets.MASTER_TOKEN }}" \
          | jq -r '.token')
        echo "::add-mask::$TOKEN"
        echo "temp-token=$TOKEN" >> $GITHUB_OUTPUT
    
    - name: Use temporary credentials
      env:
        TEMP_TOKEN: ${{ steps.temp-creds.outputs.temp-token }}
      run: |
        # Use temporary token for deployment
        ./deploy.sh</code></pre>

<p>By following these practices, we ensure that sensitive information is properly protected while maintaining the flexibility needed for automated deployments.</p>
</div>

### 39. How do you enable approvals in GitHub Actions? ✅
<div class="answer">
<p>GitHub Actions provides several mechanisms to implement approval workflows for deployments and sensitive operations. Here's how to set them up:</p>

<p><strong>1. Environment Protection Rules</strong></p>
<p>The primary method for implementing approvals in GitHub Actions is through environment protection rules.</p>

<p><strong>Setting up Environment Approvals:</strong></p>
<ol>
<li>Go to repository Settings > Environments</li>
<li>Create or select an environment (e.g., "production")</li>
<li>Configure protection rules:
  <ul>
    <li><strong>Required reviewers</strong>: Specify users/teams who must approve</li>
    <li><strong>Wait timer</strong>: Add delay before deployment</li>
    <li><strong>Deployment branches</strong>: Restrict which branches can deploy</li>
  </ul>
</li>
</ol>

<p><strong>Using Environment in Workflow:</strong></p>
<pre><code>jobs:
  deploy-production:
    runs-on: ubuntu-latest
    environment: 
      name: production
      url: https://myapp.example.com
    steps:
    - name: Deploy to production
      run: |
        echo "Deploying to production environment"
        # Deployment steps here</code></pre>

<p><strong>2. Multiple Environment Approval Chain</strong></p>
<pre><code>jobs:
  deploy-staging:
    runs-on: ubuntu-latest
    environment: staging
    steps:
    - name: Deploy to staging
      run: echo "Deploying to staging"

  deploy-production:
    needs: deploy-staging
    runs-on: ubuntu-latest
    environment: production
    steps:
    - name: Deploy to production
      run: echo "Deploying to production"</code></pre>

<p><strong>3. Manual Workflow Dispatch with Approvals</strong></p>
<pre><code>name: Manual Deployment

on:
  workflow_dispatch:
    inputs:
      environment:
        description: 'Environment to deploy to'
        required: true
        default: 'staging'
        type: choice
        options:
        - staging
        - production
      version:
        description: 'Version to deploy'
        required: true
        type: string

jobs:
  deploy:
    runs-on: ubuntu-latest
    environment: ${{ github.event.inputs.environment }}
    steps:
    - name: Deploy version ${{ github.event.inputs.version }}
      run: |
        echo "Deploying version ${{ github.event.inputs.version }} to ${{ github.event.inputs.environment }}"</code></pre>

<p><strong>4. Issue-Based Approval Workflow</strong></p>
<pre><code>name: Issue-Based Deployment

on:
  issues:
    types: [labeled]

jobs:
  deploy:
    if: contains(github.event.label.name, 'deploy-approved')
    runs-on: ubuntu-latest
    environment: production
    steps:
    - name: Extract deployment info
      id: info
      run: |
        # Parse issue body for deployment details
        VERSION=$(echo "${{ github.event.issue.body }}" | grep "Version:" | cut -d' ' -f2)
        echo "version=$VERSION" >> $GITHUB_OUTPUT
    
    - name: Deploy
      run: |
        echo "Deploying version ${{ steps.info.outputs.version }}"
        # Add deployment steps
    
    - name: Update issue
      uses: actions/github-script@v7
      with:
        script: |
          github.rest.issues.createComment({
            issue_number: context.issue.number,
            owner: context.repo.owner,
            repo: context.repo.repo,
            body: '✅ Deployment completed successfully!'
          })</code></pre>

<p><strong>5. Pull Request Based Approvals</strong></p>
<pre><code>name: PR-Based Deployment

on:
  pull_request:
    types: [closed]
    branches: [main]

jobs:
  deploy:
    if: github.event.pull_request.merged == true
    runs-on: ubuntu-latest
    environment: production
    steps:
    - name: Check PR approvals
      uses: actions/github-script@v7
      with:
        script: |
          const reviews = await github.rest.pulls.listReviews({
            owner: context.repo.owner,
            repo: context.repo.repo,
            pull_number: context.payload.pull_request.number
          });
          
          const approvals = reviews.data.filter(review => review.state === 'APPROVED');
          if (approvals.length < 2) {
            core.setFailed('At least 2 approvals required for production deployment');
          }
    
    - name: Deploy to production
      run: echo "Deploying to production"</code></pre>

<p><strong>6. Slack Integration for Approvals</strong></p>
<pre><code>jobs:
  request-approval:
    runs-on: ubuntu-latest
    steps:
    - name: Request approval via Slack
      uses: 8398a7/action-slack@v3
      with:
        status: custom
        custom_payload: |
          {
            text: "Deployment approval requested",
            attachments: [{
              color: "warning",
              fields: [{
                title: "Environment",
                value: "Production",
                short: true
              }, {
                title: "Version",
                value: "${{ github.sha }}",
                short: true
              }],
              actions: [{
                type: "button",
                text: "Approve",
                url: "https://github.com/${{ github.repository }}/actions/runs/${{ github.run_id }}"
              }]
            }]
          }
      env:
        SLACK_WEBHOOK_URL: ${{ secrets.SLACK_WEBHOOK_URL }}

  deploy:
    needs: request-approval
    runs-on: ubuntu-latest
    environment: production
    steps:
    - name: Deploy
      run: echo "Deploying after approval"</code></pre>

<p><strong>7. Advanced Approval Patterns</strong></p>

<p><strong>Time-based Approvals:</strong></p>
<pre><code>jobs:
  deploy:
    runs-on: ubuntu-latest
    environment: production
    steps:
    - name: Check business hours
      run: |
        HOUR=$(date +%H)
        DAY=$(date +%u)
        if [ $DAY -gt 5 ] || [ $HOUR -lt 9 ] || [ $HOUR -gt 17 ]; then
          echo "Deployment outside business hours requires additional approval"
          exit 1
        fi
    
    - name: Deploy
      run: echo "Deploying during business hours"</code></pre>

<p><strong>Conditional Approvals:</strong></p>
<pre><code>jobs:
  deploy:
    runs-on: ubuntu-latest
    environment: ${{ github.ref == 'refs/heads/main' && 'production' || 'staging' }}
    steps:
    - name: Deploy
      run: |
        if [ "${{ github.ref }}" == "refs/heads/main" ]; then
          echo "Production deployment (requires approval)"
        else
          echo "Staging deployment (no approval required)"
        fi</code></pre>

<p><strong>Best Practices for Approvals:</strong></p>
<ul>
<li><strong>Clear approval criteria</strong>: Define who can approve and under what conditions</li>
<li><strong>Audit trail</strong>: Maintain records of who approved what and when</li>
<li><strong>Emergency procedures</strong>: Have a process for emergency deployments</li>
<li><strong>Notification system</strong>: Alert relevant stakeholders about pending approvals</li>
<li><strong>Timeout handling</strong>: Set reasonable timeouts for approval requests</li>
</ul>

<p>These approval mechanisms help ensure that critical deployments are properly reviewed and authorized before execution.</p>
</div>

### 40. What is the folder path for action.yaml file? 📁
<div class="answer">
<p>The <code>action.yaml</code> (or <code>action.yml</code>) file is used to define custom GitHub Actions and must be placed in specific folder structures depending on the type of action you're creating.</p>

<p><strong>1. Repository Root Level (for Action Repositories)</strong></p>
<p>For repositories that contain a single action:</p>
<pre><code>my-action-repo/
├── action.yaml          # Main action definition
├── index.js            # JavaScript action code
├── package.json        # Dependencies
└── README.md           # Documentation</code></pre>

<p><strong>2. Subdirectory Structure (for Multiple Actions)</strong></p>
<p>For repositories containing multiple actions:</p>
<pre><code>my-actions-repo/
├── setup-node/
│   ├── action.yaml     # Setup Node.js action
│   └── index.js
├── deploy-app/
│   ├── action.yaml     # Deploy application action
│   └── index.js
└── README.md</code></pre>

<p><strong>3. Local Actions in Workflow Repository</strong></p>
<p>For actions used within the same repository as workflows:</p>
<pre><code>my-project/
├── .github/
│   ├── workflows/
│   │   └── ci.yml      # Workflow files
│   └── actions/        # Local actions directory
│       ├── setup-app/
│       │   ├── action.yaml
│       │   └── index.js
│       └── deploy/
│           ├── action.yaml
│           └── script.sh
├── src/
└── README.md</code></pre>

<p><strong>4. Using Local Actions in Workflows</strong></p>
<pre><code># .github/workflows/ci.yml
name: CI Pipeline

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v4
    
    # Using local action from .github/actions/setup-app/
    - name: Setup Application
      uses: ./.github/actions/setup-app
      with:
        node-version: '18'
    
    # Using local action from .github/actions/deploy/
    - name: Deploy Application
      uses: ./.github/actions/deploy
      with:
        environment: 'staging'</code></pre>

<p><strong>5. Example action.yaml Structure</strong></p>
<pre><code># .github/actions/setup-app/action.yaml
name: 'Setup Application'
description: 'Setup Node.js and install dependencies'
author: 'Your Name'

inputs:
  node-version:
    description: 'Node.js version to use'
    required: false
    default: '18'
  cache-dependency-path:
    description: 'Path to package-lock.json or yarn.lock'
    required: false
    default: 'package-lock.json'

outputs:
  cache-hit:
    description: 'Whether dependencies were restored from cache'
    value: ${{ steps.cache.outputs.cache-hit }}

runs:
  using: 'composite'
  steps:
    - name: Setup Node.js
      uses: actions/setup-node@v4
      with:
        node-version: ${{ inputs.node-version }}
        cache: 'npm'
        cache-dependency-path: ${{ inputs.cache-dependency-path }}
    
    - name: Install dependencies
      run: npm ci
      shell: bash

branding:
  icon: 'package'
  color: 'blue'</code></pre>

<p><strong>6. Docker Action Structure</strong></p>
<pre><code>my-docker-action/
├── action.yaml         # Action definition
├── Dockerfile          # Docker container definition
├── entrypoint.sh       # Entry point script
└── README.md</code></pre>

<p><strong>Example Docker action.yaml:</strong></p>
<pre><code># action.yaml
name: 'Docker Action Example'
description: 'A Docker-based action'

inputs:
  command:
    description: 'Command to run'
    required: true

outputs:
  result:
    description: 'Command output'

runs:
  using: 'docker'
  image: 'Dockerfile'
  args:
    - ${{ inputs.command }}</code></pre>

<p><strong>7. JavaScript Action Structure</strong></p>
<pre><code>my-js-action/
├── action.yaml         # Action definition
├── index.js           # Main JavaScript file
├── package.json       # Node.js dependencies
├── node_modules/      # Dependencies (should be committed)
└── README.md</code></pre>

<p><strong>8. Composite Action Structure</strong></p>
<pre><code>my-composite-action/
├── action.yaml         # Composite action definition
├── scripts/
│   ├── setup.sh
│   └── deploy.sh
└── README.md</code></pre>

<p><strong>Key Points about action.yaml Placement:</strong></p>
<ul>
<li><strong>File naming</strong>: Can be either <code>action.yaml</code> or <code>action.yml</code></li>
<li><strong>Root requirement</strong>: Must be in the root of the action directory</li>
<li><strong>Referencing</strong>: Actions are referenced by their directory path</li>
<li><strong>Versioning</strong>: Use Git tags for versioning published actions</li>
<li><strong>Marketplace</strong>: Actions in repository root can be published to GitHub Marketplace</li>
</ul>

<p><strong>Best Practices:</strong></p>
<ul>
<li>Use descriptive directory names for actions</li>
<li>Include comprehensive documentation in README.md</li>
<li>Test actions thoroughly before publishing</li>
<li>Use semantic versioning for action releases</li>
<li>Keep action.yaml files well-documented with descriptions</li>
</ul>

<p>The correct placement of action.yaml files is crucial for GitHub Actions to properly recognize and execute your custom actions.</p>
</div>

---

<div align="center">
  <p><strong>🎉 Congratulations! You've completed the Azure DevOps & GitHub Actions Interview Guide! 🎉</strong></p>
  <p>For more resources and updates, visit <a href="https://saanvikit.com">https://saanvikit.com</a></p>
  <p>Contact: +91 9513184144</p>
</div>
