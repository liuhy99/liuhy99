## Hi there 👋

<!--
**liuhy99/liuhy99** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->

name: Update gist with WakaTime stats
on:
  schedule:
    - cron: "0 0 * * *"
  # Manual triggers with workflow_dispatch
  workflow_dispatch:
jobs:
  update-gist:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@master
      - name: Update gist
        uses: matchai/waka-box@master
        env:
          GH_TOKEN: ${{ secrets.GH_TOKEN }}
          GIST_ID: 968220c97e8da1d047a9a480fa432e54
          WAKATIME_API_KEY: ${{ secrets.WAKATIME_API_KEY }}
