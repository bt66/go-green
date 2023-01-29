<h1>Auto commit bot.</h1>
<h2>this repo is used for auto commit and push to repository</h2>
<p>go-green auto commit using github action to automatically commit and push</p>
<p>i use cronjob and repository_dispatch to trigger action periodly, repository_dispatch make possibility to trigger action by rest api requests</p>
<p>repository_dispatch is optional, i used it because github schedule with cron not always run cron on time</p>

<p>this is example of rest api request if you use repository_dispatch to trigger github action</p>

```bash
curl -H "Accept: application/vnd.github.everest-preview+json" \
    -H "Authorization: token <replace this with github token>" \
    --request POST \
    --data '{"event_type": "start-action"}' \
    https://api.github.com/repos/<your github username>/<your github repository name>/dispatches
```

<p>so if i need to trigger this github action in this repository, the request will look like bellow :</p>
```bash
curl -H "Accept: application/vnd.github.everest-preview+json" \
    -H "Authorization: token <replace this with github token>" \
    --request POST \
    --data '{"event_type": "start-action"}' \
    https://api.github.com/repos/bt66/go-green/dispatches
```