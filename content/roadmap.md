---
title: Roadmap
mermaid: true
---

This is a roadmap of what I'm learning, and what I've learned, what I'm reading, and what I've read. It's not really a roadmap to anything specifically, though it may turn into one eventually. For now, it's just a 'roadmap' of everything. I may refer to it as a roadmap for developers, but the 'development' here is of a general kind. Everything from developing Excel charts to developing programs.

{{< mermaid >}}
flowchart TD
	132336["Physics\n"] --> 839633["General Introduction"]
	750029["Calculus"] -.-> 839633
	750029 --> 443207["Differential Equations"]
	443207 --> 780623["Discrete Mathematics\n(Mathematics for Computer Science \nEric Lehman, et. al)\n"]
	780623 --> 473215["Linear Algebra"]
	473215 --> 336082["Probability & Statistics"]
	915323["Finance"] --> 893308["Budgeting\n(You Need a Budget\nJesse Mecham)\n"]
	150733["Investing\n"] --> 346835["The Intelligent Investor\nBenjamin Graham"]
	915323 --> 150733
	312968["Sciences"] --> B("Mathematics")
	312968 --> 132336
	144730["Lifestyle"] --> 915323
	150733 --> 910954["The Little Book of Common-Sense Investing\nJohn C. Bogle"]
	144730 --> 857940["Menswear"]
	857940 --> 107149["Ametoro\nDavid W. Marx"]
	312968 --> 160031["Economics\n"]
	B --> 289800["Precalculus"]
	style 289800 stroke:#000000,fill:#00ff24,stroke-width: 2px,color:#000000
	289800 --> 750029
	160031 --> 154350["Economics in One Lesson\nHenry Hazlitt"]
	style 154350 stroke-width: 2px,fill:#1dff12,color:#000000
{{< /mermaid >}}