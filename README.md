# rails\_activejob\_example

This was forked from https://github.com/engineyard/rails_activejob_example/tree/sidekiq, a minimalist Rails application created to test background workers on Engine Yard Cloud.

This is a playground project designed to get you up to speed with Sidekiq and Rails background jobs.

## Quick Start

1) Recommended: clone your fork of the project instead

```
git clone git@github.com:radamanthus/rails_activejob_example.git
```

2) Setup the project gems

```
bundle install
```

3) Create the project database. Make sure both Redis and PostgreSQL are running first.

```
bundle exec rake db:create
```

4) Generate jobs

```
ECHO_JOB_COUNT=10 bundle exec rake echo:generate
```

5) Run a sidekiq worker

```
bundle exec sidekiq
```

## Useful Links

Rails ActiveJob: http://edgeguides.rubyonrails.org/active_job_basics.html

Sidekiq: https://github.com/mperham/sidekiq

Redis: https://redis.io/

## Questions

1) What are the performance characteristics of Redis that make it ideal for queue storage?

2) What happens if Sidekiq encounters an exception while running a job?
Hint: https://github.com/mperham/sidekiq/wiki/Error-Handling

3) What happens if the Sidekiq worker process dies while running a job?
Hint: https://github.com/mperham/sidekiq/wiki/Error-Handling#process-crashes

## Exercises

1) Add some ActiveRecord objects to the Rails application. Then create a new Sidekiq job class that loads an ActiveRecord object and updates it. How different is your new job class from EchoJob?

2) Modify EchoJob to throw an exception every time it runs a job. Visit the Sidekiq dashboard in http://localhost:3000/sidekiq and rerun the job.

