[![Welcome to my GitHub!](https://img.shields.io/badge/Welcome%20to%20my%20GitHub!-0099ff?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Nuruzzaman-Nuru)

-  Hi, I’m Nurzaman-Nuru  
- 🎓 Studying at Green University of Bangladesh  
- 👀 I’m interested in Web Development  
[![Portfolio](https://img.shields.io/badge/Portfolio-visit%20now-0A66C2?style=for-the-badge&logo=Firefox-Browser&logoColor=white)](https://nurzamanportfolio.vercel.app/)

[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/nuruzzaman2222/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/md-nurzaman-7b9858262/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Nuruzzaman-Nuru)
[![Facebook](https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white)](https://www.facebook.com/nuruzzaman6868/)

import React, { useEffect, useState } from "react";

// Nuruzzaman-Nuru গিটহাব ইউজারনেম এখানে সেট করা:
const GITHUB_USERNAME = "Nuruzzaman-Nuru";

export default function ContributionChat() {
  const [contributions, setContributions] = useState([]);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    fetch(`https://api.github.com/users/${GITHUB_USERNAME}/events/public`)
      .then((res) => res.json())
      .then((data) => {
        // সর্বশেষ ৫টি ইভেন্ট শো করবে
        const items = data.slice(0, 5).map((item) => {
          let message = "";
          if (item.type === "PushEvent") {
            message = `Pushed ${item.payload.commits.length} commits to ${item.repo.name}`;
          } else if (item.type === "PullRequestEvent") {
            message = `${item.payload.action === "opened" ? "Opened" : "Updated"} a pull request #${item.payload.number} in ${item.repo.name}`;
          } else if (item.type === "IssuesEvent") {
            message = `${item.payload.action === "opened" ? "Created" : "Updated"} issue #${item.payload.issue.number} in ${item.repo.name}`;
          } else if (item.type === "IssueCommentEvent") {
            message = `Commented on issue #${item.payload.issue.number} in ${item.repo.name}`;
          } else if (item.type === "PullRequestReviewEvent") {
            message = `Reviewed PR #${item.payload.pull_request.number} in ${item.repo.name}`;
          } else {
            message = `${item.type} in ${item.repo.name}`;
          }
          return {
            date: item.created_at.slice(0, 10),
            message,
          };
        });
        setContributions(items);
        setLoading(false);
      });
  }, []);

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
      {loading ? <div>Loading...</div> : (
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
      )}
    </div>
  );
}
