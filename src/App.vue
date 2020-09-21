<template>
  <div id="app">
    <h1>Git Cheat Sheet</h1>

    <GitCommandsList title="Git Basic" :commands="gitBasic" />

    <GitCommandsList title="Annulation des moficiation" :commands="gitUndoingChanges" />
    <GitCommandsList title="Réecrire l'historique" :commands="gitRewritingHistory" />
    <GitCommandsList title="Git Branches" :commands="gitBranches" />
    <GitCommandsList title="Dépôts Distants" :commands="gitRemoteRepositories" />

    <br />
    <h1>Options additionnels</h1>

    <GitCommandsList title="Git Config" :commands="gitConfig" />
    <GitCommandsList title="Git Log" :commands="gitLog" />
    <GitCommandsList title="Git Diff" :commands="gitDiff" />
    <GitCommandsList title="Git Reset" :commands="gitReset" />
    <GitCommandsList title="Git Rebase" :commands="gitRebase" />
    <GitCommandsList title="Git Pull" :commands="gitPull" />
    <GitCommandsList title="Git Push" :commands="gitPush" />
  </div>
</template>

<script>
import gitBasic from "./git-basic.json";
import gitUndoingChanges from "./git-undoing-changes.json";
import gitRewritingHistory from "./git-rewriting-history.json";
import gitBranches from "./git-branches.json";
import gitRemoteRepositories from "./git-remote-repositories.json";
import gitConfig from "./git-config.json";
import gitLog from "./git-log.json";
import gitDiff from "./git-diff.json";
import gitReset from "./git-reset.json";
import gitRebase from "./git-rebase.json";
import gitPull from "./git-pull.json";
import gitPush from "./git-push.json";
import GitCommandsList from "./components/GitCommandsList";
export default {
  name: "App",
  components: { GitCommandsList },
  data: () => {
    return {
      gitBasic,
      gitUndoingChanges,
      gitRewritingHistory,
      gitBranches,
      gitRemoteRepositories,
      gitConfig,
      gitLog,
      gitDiff,
      gitReset,
      gitRebase,
      gitPull,
      gitPush
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
