# Want to help?

If you'd like to contribute to the web site, there are a couple of options.

## If you've never used Github

  1. [Create a Github account](https://github.com/join).
  2. [Join us on Slack](https://legacyofchaoshome.slack.com/).
  3. Post your Github username on `#website_of_chaos`, and let us know you'd like to contribute.
     You should probably mention `@armandz` and `@kungfugrip` to get our attention.
  4. After getting approval from `@armandz`, we'll add you as a contributor.
  5. You can use Github to update files in the repo directly, no knowledge of `git` 
     required! ...but you **really** should [learn the basics](https://guides.github.com/activities/hello-world/).

## If you're comfortable with Github

  1. You should try [Github Desktop](https://desktop.github.com/) if your `git`-fu isn't super strong.
  2. [Atom](https://atom.io/) is a fantastic editor, plus 
     [it has git integration](https://www.youtube.com/watch?v=7FPTUaoHtjQ) after v1.18.
  3. [Play some funky beats](https://www.youtube.com/watch?v=ns3SAjqMGU0&index=10&list=PL7-NrfuNPRyyClJ3M_suEWEzIVJWr6HAA), 
     and get to coding.
     
Or, you could fork the repo, make your changes, and issue a pull request.

## If you're a "get off my lawn" kind of grey beard

[Add your SSH public key to your Github account](https://github.com/settings/keys),
and then clone the repo.

    mkdir -p ~/src && cd $_
    git clone git@github.com:JasonSFuller/chaos.thriii.com.git
    cd chaos.thriii.com

If your global `git` settings aren't appropriate, you can change the local settings for this single repository.

    git config user.name  "your-github-username"
    git config user.email "your-personal-email@example.com"

Make your changes.  If you're branching, make sure they make it into the `master` branch.
Then push your changes back up to Github.

    git add .
    git status
    git commit -m 'description of your changes'
    git push origin master

# How does it work?

When changes are committed to the `master` branch on Github, a [webhook](https://developer.github.com/webhooks/) 
on this repo notifies my web server.  My web server issues a `git pull` on 
[guildsofchaos.com](http://www.guildsofchaos.com/)'s [DocumentRoot](http://httpd.apache.org/docs/2.2/mod/core.html#documentroot), 
and _voila_, the web site is updated.
