<template>
  <div id="app">
    <div class="page">
      <h1>Git Cheat Sheet</h1>

      <h2>Pratique de base</h2>

      <p>
        Sur un projet sous git, lorsque l'on travaille à plusieurs sur un projet, il est souvent nécessaire de
        travailler chacun sur sa branche pendant
        le développement et ensuite d'intégrer les modifications dans une branche commune.
      </p>

      <p>
        La branche
        <b>master</b> représente la branche de production.
        <br/>La branche
        <b>develop</b> représente la branche de développement, c'est sur celle-ci que l'on doit intégrer nos
        modifications.
      </p>

      <h3>Déroulement d'un dévelopement sous Git</h3>

      <p>
        Dans notre exemple, nous devons développer la possibilité de modifier les mots de passes des utilisateurs.
        <br>On se met sur la branche
        <b>develop</b>.
        <br>On récupère éventuellement les modifications pour être à jour sur la branche (git fetch, git pull).
        <br>On crée sa branche (git checkout -b features/password-request).
        <br>
        <br>On peut push la branche nouvellement créer avec 'git push --set-upstream &lt;remote&gt; features/password-request'.
        <br>Une fois la branche créée, on peut ajouter nos premiers commit.
        <br>
        <br>Une fois la branche terminée, il suffit de créer une pull request sur l’interface web (Github, Gitlab etc.)
        et faire la demande de merge dans la branche
        <b>develop</b>.
      </p>

      <h3>Faire un hotfix</h3>
      <p>Parfois il arrive que des problèmes remontent dans l'environnement de production. Une branche "hotfix" est
        alors utilisé pour corriger ces problèmes.<br>
        Cette branche part de 'master' et est fusionnée avec la branche de développement et la branche de
        production.<br>
      </p>
      <code>
        git flow hotfix start hotfix-name
      </code>
      <p>Une fois la branche crée, on effectue les modifications dans cette branche de hotfix. Pour terminer le hotfix
        il suffit de faire</p>
      <code>
        git flow hotfix finish 'hotfix-name'
      </code>
    </div>
    <div class="page">
      <h1>Commande de bases</h1>
      <div class="list-commands">
        <GitCommandsList title="Git Basic" :commands="gitBasic"/>
        <GitCommandsList title="Annulation des modificiations" :commands="gitUndoingChanges"/>
        <GitCommandsList title="Réécrire l'historique" :commands="gitRewritingHistory"/>
        <GitCommandsList title="Git Branches" :commands="gitBranches"/>
        <GitCommandsList title="Dépôts Distants" :commands="gitRemoteRepositories"/>
      </div>
    </div>
    <br/>
    <div class="page">
      <h1>Options additionnels</h1>

      <div class="list-commands">
        <GitCommandsList title="Git Config" :commands="gitConfig"/>
        <GitCommandsList title="Git Log" :commands="gitLog"/>
        <GitCommandsList title="Git Diff" :commands="gitDiff"/>
        <GitCommandsList title="Git Reset" :commands="gitReset"/>
        <GitCommandsList title="Git Rebase" :commands="gitRebase"/>
        <GitCommandsList title="Git Pull" :commands="gitPull"/>
        <GitCommandsList title="Git Push" :commands="gitPush"/>
      </div>
    </div>
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
  components: {GitCommandsList},
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
      gitPush,
    };
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  max-width: 1830px;
  margin: auto;
}

.list-commands {
  display: grid;
  flex-wrap: wrap;
  grid-gap: 10px;
  grid-template-columns: 50% 50%;
}

.page {
  break-after: always;
  page-break-after: always;
}
</style>
