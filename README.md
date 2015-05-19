# Decoupling the CMS with React and CouchDB

## The website
  Drupal 7 with normal set up. Nothing fancy in it.
  The site is a blog with a few custom pages and forms.

# The goal
  * Give the design and front end team freedom to design the
    front without the constraints of the CMS.
  * Empower the articles section since they our main source of traffic.
  * Only anonymous navigation in the front end.

# The project
  * Drupal to just serve as a CMS.
  * Drupal to export data to CouchDB on cron run.
  * The front end to fetch the data from CouchDB.
  * The front end to be an isomorphic application written in NodeJS
    & React. No JQuery.

# The back end
  * Show an article form.
  * Explain the section for React.
    * Parent is used to build a path such as articles/article-slug.
    * Slug is the friendly identifier.
    * Full slug is used to identify an article.
    * Template defines which template should React use to render it.

# The front end
  * Show the article page.
  * Show the template structure in React.
  * Show how React can be called by the server and the browser.
  * Show the query to CouchDB to retrieve the article.

# The middleware
  * Node insert/update > push to queue.
  * Cron run > export to CouchDB.
  * Redirects in CouchDB.

# Forms
  * Comments > Disqus.
  * MailChimp > form sent to NodeJS, which submits it through MCAPI.
  * Contact form > sent to NodeJS, which sends an email.

# Deployments
  * Jenkins job for back end:
    1. Check out tag.
    2. make (updb, fra, cc all).
  * Jenkins job for front end:
    1. Check out to release directory.
    2. make (npm install, bower install, grunt).
    3. Replace symlink to web root.
    4. Restart NodeJS application.

# Next steps
  * Upgrade the back end to Drupal 8.
  * Conquer the world!
  * No user session. What if we need it?
  * No site preview. How can we let editors preview an article?
