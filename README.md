[![Welcome to my GitHub!](https://img.shields.io/badge/Welcome%20to%20my%20GitHub!-0099ff?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Nuruzzaman-Nuru)

-  Hi, I’m Nurzaman-Nuru  
- 🎓 Studying at Green University of Bangladesh  
- 👀 I’m interested in Web Development  
[![Portfolio](https://img.shields.io/badge/Portfolio-visit%20now-0A66C2?style=for-the-badge&logo=Firefox-Browser&logoColor=white)](https://nurzamanportfolio.vercel.app/)

[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/nuruzzaman2222/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/md-nurzaman-7b9858262/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Nuruzzaman-Nuru)
[![Facebook](https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white)](https://www.facebook.com/nuruzzaman6868/)

import React from "react";

export default function MyGithubStats() {
  // আপনার তথ্য এখানে বসান
  const stats = {
    name: "Nuruzzaman Nuru's GitHub Stats",
    stars: "1.1k",
    commits: 720,
    prs: 7,
    issues: 2,
    contributed: 11,
    grade: "A-"
  };

  return (
    <div style={{
      border: "1px solid #e1e4e8",
      borderRadius: 8,
      padding: 24,
      width: 380,
      background: "#fff",
      fontFamily: "Segoe UI, sans-serif",
      boxShadow: "0 1px 3px rgba(0,0,0,0.05)"
    }}>
      <div style={{fontWeight: 600, fontSize: 18, color: "#0366d6", marginBottom: 16}}>
        {stats.name}
      </div>
      <div style={{display: "flex", alignItems: "center"}}>
        <div style={{flex: 1}}>
          <div>⭐ <b>Total Stars Earned:</b> <span style={{float: "right"}}>{stats.stars}</span></div>
          <div>⏰ <b>Total Commits (2025):</b> <span style={{float: "right"}}>{stats.commits}</span></div>
          <div>🔀 <b>Total PRs:</b> <span style={{float: "right"}}>{stats.prs}</span></div>
          <div>❗ <b>Total Issues:</b> <span style={{float: "right"}}>{stats.issues}</span></div>
          <div>🖥️ <b>Contributed to (last year):</b> <span style={{float: "right"}}>{stats.contributed}</span></div>
        </div>
        {/* গ্রেড সার্কেল */}
        <div style={{
          width: 80, height: 80, borderRadius: "50%",
          border: "7px solid #3688e3", marginLeft: 24,
          display: "flex", alignItems: "center", justifyContent: "center",
          fontSize: 28, color: "#3688e3", fontWeight: 700,
          background: "#f6f8fa"
        }}>
          {stats.grade}
        </div>
      </div>
    </div>
  );
}
