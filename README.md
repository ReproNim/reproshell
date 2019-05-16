# reproshell
Shell (bash only ATM) configuration to facilitate reproducible research

# Perspective features

Although some features are inspired by prototype implementation to be used within singularity container environments, they are applicable for any, even direct invocation.

- **Deployment**
  - [ ] could be used as a standalone configuration
  - [ ] could be "pluggable", i.e. the shell configuration to use within containers and remote sessions while "interfacing back" various session artifacts (e.g., history)
- **Features**, most of which should be configurable from outside (for "pluggable" mode of operation)
  - [ ] **infinite shell history** (unless explicitly requested to be session only, e.g. within container run)
  - [ ] **VCS support** (to show when under some VCS and in what branch/state it is)
  - **avoidance of session/execution side-effects**
   - [ ] isolated `/tmp`
   - [ ] (optionally) isolated `$HOME`? so no side-effects from `~/.local` installations etc
   - [ ] (optionally) sanitized environment variables
  - **informative and pretty (to >80% of users) prompt**
   - PS1 should should
    - [ ] show being under some container/conda/virtualenv environment
    - [ ] show full current path
    - [ ] show user (in particular when root)
    - [ ] (may be) # of commands in the history
   - additional "pluggable" indicators, such as 
    - [ ] being in a session traced by reprozip or reproman.
    - [ ] being outside of a set of "tracked" directories (e.g., within `datalad run` execution)
  - **integrations**
   - [ ] `datalad containers-run` or ReproNim/containers to replace parts of the custom .bashrc/singularity_run prototype
   - [ ] `reproman execute` and possibly `run` to provide consistent interface across wide range of resources
   - Metrics collection
    - [ ] could be the one to remind users whenever popularity-contest or our custom usage reporting facility is not enabled
   - [ ] (may be) even activate/deactivate handling for pluggable indicators etc (e.g. to enable/disable tracing)
   - [ ] could collect (and later aggregate/join) DueCredit reports from interim executions
   - [ ] may be optionally could be made persistent via starting actual session under screen or tmux.  Then could come with some custom nice .screenrc settings to visualize current load/

So, some features (infinite history, VCS integration, may be color scheme) could be provided by bundling existing 3rd party projects.  The rest more custom

## References
- Recommended .bashrc to assist in facilitating moer efficient shell and bash history use and archival:  https://github.com/ReproNim/module-reproducible-basics/pull/26
- Recording bash sessions history within git during interactive `datalad containers-run` https://github.com/ReproNim/containers/pull/9
