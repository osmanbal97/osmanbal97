[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs?username=osmanbal97&layout=compact&hide_title=false&card_width=360&langs_count=8&theme=react&hide_border=false&countprivate=true)](https://github.com/osmanbal97/github-readme-stats)

query userInfo($login: String!) {
  user(login: $login) {
    # fetch only owner repos & not forks
    repositories(ownerAffiliations: OWNER, isFork: false, first: 100) {
      nodes {
        name
        languages(first: 10, orderBy: {field: SIZE, direction: DESC}) {
          edges {
            size
            node {
              color
              name
            }
          }
        }
      }
    }
  }
}
