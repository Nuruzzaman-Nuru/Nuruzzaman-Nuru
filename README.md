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

const contributions = [
  { date: "2025-08-10", message: "Pushed 3 commits to main" },
  { date: "2025-08-11", message: "Opened a pull request #12" },
  { date: "2025-08-12", message: "Reviewed PR #10" },
  { date: "2025-08-13", message: "Created issue #15" },
  { date: "2025-08-14", message: "Closed issue #13" },
];

export default function ContributionChat() {
  return (
    <div style={{
      background: "#22272e",
      color: "#adbac7",
      padding: 16,
      borderRadius: 8,
      width: 350,
      fontFamily: "monospace"
    }}>
      <h3 style={{marginTop:0}}>🗨️ Contribution Activity</h3>
      <div>
        {contributions.map((contrib, idx) => (
          <div key={idx} style={{
            margin: "12px 0",
            borderLeft: "3px solid #539bf5",
            paddingLeft: 12
          }}>
            <div style={{fontSize: 12, color: "#768390"}}>{contrib.date}</div>
            <div>{contrib.message}</div>
          </div>
        ))}
      </div>
    </div>
  );
}

