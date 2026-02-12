name: Update Latest Publications
on:
  schedule:
    - cron: '0 0 * * *' # Roda todo dia à meia-noite
  workflow_dispatch:

jobs:
  update-readme-with-blog:
    name: Update this repo's README with latest blog posts
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: gautamkrishnar/blog-post-workflow@master
        with:
          feed_list: "https://medium.com/feed/@therviahealthtech" # Coloque o RSS da Thervia aqui
