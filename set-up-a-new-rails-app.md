# Set up a new Rails app

----

In a Terminal window, navigate to your coding directory.
  - eg `cd coding/personal/`

If your app will be called, eg `sophie`, run:
  - `suspenders sophie`

The suspenders script will install a fresh Rails app in a new `sophie` folder. When it's finished, run `ls` to see the new folder. Step into it with:
- `cd sophie`

Suspenders also initialized a Git repository. Make your initial commit:
- `git add .`
- `git commit -m "Initial commit"`

In a browser window, log in to Github.

Create a new repository.
- Do not initialize with a readme, gitignore or license.

Copy the SSH URL for the repository.
- eg `git@github.com:keiranking/sophie.git`

Return to Terminal and paste the SSH URL into the following command:
- `git remote add origin git@github.com:keiranking/sophie.git`
- `git remote -v`
- `git push -u origin master`

Open another Terminal window and navigate to your project folder. Start a Rails server.
- eg `rails server -p 3001`

In a browser window, navigate to `localhost:3001`. You should see the Rails success page.

Log in to Heroku. Create a new app.
- eg `sophie-staging`

In Terminal, authenticate and establish your Heroku app as a remote for your project.
- `heroku login`
  (Type Heroku username and password when prompted. Your password will not appear even though the keystrokes are being registered. 2-factor authentication can be done using the Authy app on your phone.)
- `heroku git:remote -a sophie-staging`
- `git remote -v`
- `git remote rename heroku staging`
<!-- - `git push staging` -->

On Heroku's Dashboard > Settings in your browser:
- Add Ruby buildpack
- Add Nodejs buildpack

Add environment (config) variables in your Heroku Dashboard:
- `ASSET_HOST: sophie-staging.herokuapp.com`
- `APPLICATION_HOST: sophie-staging.herokuapp.com`
- `SMTP_ADDRESS: smtp.example.com`
- `SMTP_DOMAIN: example.com`
- `SMTP_USERNAME: username`
- `SMTP_PASSWORD: password`

In a code editor (eg Atom), add a line to your project `Gemfile`:
- `gem "webpacker", require: false`

In Terminal, create a new commit and then push your project to Heroku:
- `git add .`
- `git commit -m "Setup staging on Heroku"`
- `git push staging`

At this point, you should successfully deploy to Heroku. But your site will still fail to load in a browser at `sophie-staging.herokuapp.com`.

In Terminal, update your database:
- `heroku run rake db:migrate`

If your site still fails to load, type in Terminal:
- `rails g controller welcome index`

Then in your code editor:
- Open `config/routes.rb`
- Add the line `root 'welcome#index'`

Create a new commit as before, and push to staging.

Your site should deploy to Heroku, and load in a browser. If you can't load the site locally and get the error `Could not connect to server: No such file or directory. Is the server running locally and accepting connections on Unix domain socket "/tmp/.s.PGSQL.5432"`:
- In Terminal, navigate to root folder (`~%`)
- `rm /usr/local/var/postgres/postmaster.pid`
- Restart your local server
