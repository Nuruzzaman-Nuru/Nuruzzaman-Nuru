[![Welcome to my GitHub!](https://img.shields.io/badge/Welcome%20to%20my%20GitHub!-0099ff?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Nuruzzaman-Nuru)

-  Hi, I’m Nurzaman-Nuru  
- 🎓 Studying at Green University of Bangladesh  
- 👀 I’m interested in Web Development  
[![Portfolio](https://img.shields.io/badge/Portfolio-visit%20now-0A66C2?style=for-the-badge&logo=Firefox-Browser&logoColor=white)](https://nurzamanportfolio.vercel.app/)

[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/nuruzzaman2222/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/md-nurzaman-7b9858262/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Nuruzzaman-Nuru)
[![Facebook](https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white)](https://www.facebook.com/nuruzzaman6868/)

# Nuruzzaman Nuru's GitHub Profile

<div align="center">
  <img src="https://github.com/Nuruzzaman-Nuru/Nuruzzaman-Nuru/blob/main/github-stats.svg" alt="GitHub Stats" />
</div>
name: Generate GitHub Stats

on:
  schedule:
    - cron: '0 0 * * *'  # Runs every day at midnight
  workflow_dispatch:      # Allows manual trigger
  push:
    branches: [ main ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v2
    
    - name: Setup Node.js
      uses: actions/setup-node@v2
      with:
        node-version: '16'
        
    - name: Install dependencies
      run: |
        npm install react react-dom @napi-rs/canvas
        
    - name: Generate Stats
      run: node -r @napi-rs/canvas .github/scripts/generate-stats.js
      
    - name: Commit and Push
      run: |
        git config --global user.name 'GitHub Action'
        git config --global user.email 'action@github.com'
        git add .
        git commit -m "Update GitHub stats" || exit 0
        git push
