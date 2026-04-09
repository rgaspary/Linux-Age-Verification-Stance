# Linux Distros & Age Verification Laws

> **Context:** California's Digital Age Assurance Act (AB 1043), effective January 1, 2027, requires operating system providers to collect user age data at account setup and expose age-bracket signals via real-time API to app developers. Similar legislation exists in Brazil (ECA Digital, March 2026), Colorado (pending), and the UK (Online Safety Act, July 2025). This table tracks how major Linux and BSD distributions are responding.

---

## Distro Stances

| Distro | Stance | Summary | Source |
|---|---|---|---|
| **Ubuntu** | ⚠️ Reviewing | Developer Aaron Rainbolt proposed an optional D-Bus interface (`org.freedesktop.AgeVerification1`) that exposes only an age bracket — not raw personal data. Canonical confirmed awareness of the laws and is reviewing them with legal counsel, but has announced no concrete plans. | [9to5Linux](https://9to5linux.com/ubuntu-fedora-linux-mint-eye-age-verification-amid-california-law-backlash) |
| **Fedora** | ⚠️ Reviewing | Fedora Project Leader Jef Spaleta proposed a privacy-preserving local API approach — apps query Fedora for an age bracket, no telemetry required. Suggested implementation could be as simple as a new `/etc/` file populated at account creation. No formal decision made. | [9to5Linux](https://9to5linux.com/ubuntu-fedora-linux-mint-eye-age-verification-amid-california-law-backlash) |
| **Debian** | ⚠️ Investigating | The Debian Project is actively investigating whether the new age verification laws apply to its distribution. Aims to keep any such features optional while respecting the needs of users in affected jurisdictions. | [9to5Linux](https://9to5linux.com/ubuntu-fedora-linux-mint-eye-age-verification-amid-california-law-backlash) |
| **Linux Mint** | 🔇 Silent | No official statement has been made. Given its close alignment with Ubuntu, it is widely expected to follow whatever direction Canonical takes, likely adopting a similar shared API approach. | [It's FOSS](https://itsfoss.com/news/distros-response-age-verification-laws/) |
| **Arch Linux** | 🔇 Silent | No public stance. Architecturally, compliance is considered near-impossible — Arch's pacman package manager has no user account system, and ISOs are distributed anonymously via global mirrors. Forum discussions have appeared and been removed. | [LinuxTeck](https://www.linuxteck.com/california-age-verification-law-linux/) |
| **Gentoo** | 🔇 Silent | No official statement. Compliance is considered categorically incompatible with Gentoo's model — software is compiled from source, with no concept of a gated app store or centralized user accounts. | [LinuxTeck](https://www.linuxteck.com/california-age-verification-law-linux/) |
| **openSUSE** | 🔇 Silent | No official announcement. The community is actively discussing whether to include the systemd 261 birthDate field and how it interacts with upcoming laws. European-focus means less immediate pressure. | [openSUSE Forums](https://forums.opensuse.org/t/is-there-an-opensuse-announcement-regarding-the-age-verification-bills/192943) |
| **NixOS** | 🔇 Waiting | Community discussions indicate NixOS is watching and waiting to see what larger upstream distributions (Debian, Ubuntu, Fedora) decide before taking action. | [It's FOSS](https://itsfoss.com/news/distros-response-age-verification-laws/) |
| **Pop!\_OS (System76)** | ⚠️ Reluctantly Compliant | System76 CEO Carl Richell stated the company will follow applicable laws, but hopes they will "be recognized for the folly they are." System76 met with Colorado Senator Matt Ball, who proposed exempting open-source software from the bill. | [The Register](https://www.theregister.com/2026/03/13/opinion_os_verification/) |
| **Elementary OS** | ⚠️ Leaning Compliant | Has publicly discussed implementing an age-verification API, aligning with the "corporate-friendly" side of the ecosystem's philosophical split. | [grigio.org](https://grigio.org/linux-distros-resistance-against-age-verification-laws/) |
| **EndeavourOS** | ⚠️ Waiting / No Capacity | In the Titan release announcement, the team stated they were "surprised by the news" and cannot make a clear statement yet, as the decision involves DEs, software packages, and mirror networks — not just the distro itself. They noted they have no infrastructure to track users or downloads and lack the manpower to implement compliance, which they called "a near-impossible task" that goes against FOSS fundamentals. | [EndeavourOS Blog](https://endeavouros.com/news/whats-new-in-endeavouros-titan-release/) |
| **Garuda Linux** | ❌ Non-Compliant (Jurisdiction-Based) | Issued a clear official statement: infrastructure is hosted in Finland and Germany, contributors comply with their local laws (one maintainer cited Austrian law), and no U.S. or Brazilian legislation applies to them. The statement explicitly says California authorities are "free to block Garuda Linux's website in California" rather than expecting global compliance. Acknowledged that if laws passed in their own jurisdictions they would likely comply, citing the very real risk of life-changing individual fines. | [Garuda Linux Forum](https://forum.garudalinux.org/t/a-statement-on-age-verification-the-state-of-the-community-discourse/47652) |
| **Omarchy Linux (DHH)** | ❌ Non-Compliant | Creator David Heinemeier Hansson (DHH) outright rejected compliance, calling the California law "unenforceable" and expressing no intention to respond to it. | [It's FOSS](https://itsfoss.com/news/distros-response-age-verification-laws/) |
| **Adenix GNU/Linux** | ❌ Non-Compliant | Founder J. Mazzullo declared the distro "will NOT have any age checks" and that it is "not for use in regions with OS age verification laws." | [The Register](https://www.theregister.com/2026/03/13/opinion_os_verification/) |
| **Ageless Linux** | ❌ Intentionally Non-Compliant | Created expressly as a protest distro (Debian-based). Registered as an OS under AB 1043's own definitions and declared full, knowing, and intentional noncompliance on its front page. Also developing a $12 RISC-V "Ageless Device" for distribution to schools. | [It's FOSS](https://itsfoss.com/news/ageless-linux/) |
| **MidnightBSD** | ❌ Non-Compliant (License Change) | Updated its license to explicitly exclude California residents from desktop use effective January 1, 2027. Released v4.0.4 with an age attestation daemon (`aged`) that runs at startup but can be disabled. Described as a "temporary measure." | [9to5Linux](https://9to5linux.com/ubuntu-fedora-linux-mint-eye-age-verification-amid-california-law-backlash) |
| **CachyOS** | ⚠️ Ambiguous / Disputed | Based in Germany (founders in Germany & Russia), CachyOS issued a statement saying it is "not doing anything in regards to this" since age verification laws don't apply in its jurisdiction. However, the statement also told users to stop being "radical" about the topic and warned of moderation action — leading to community accusations of censorship. Because CachyOS ships systemd, it will passively inherit the `birthDate` field when systemd v261 lands. The official posture is considered internally inconsistent by many community members. | [CachyOS Forum](https://discuss.cachyos.org/t/clarification-on-age-verification-stance-and-comments/26652) |
| **Bazzite** | 🚫 Geo-Restricted | This Steam Deck-focused Fedora derivative restricted access from Brazil following the ECA Digital law that took effect in March 2026, citing legal risk. | [grigio.org](https://grigio.org/linux-distros-resistance-against-age-verification-laws/) |

---

## Upstream / Infrastructure

| Project | Action | Source |
|---|---|---|
| **systemd** | Merged optional `birthDate` field for user accounts in v261 (March 2026). Admins-only write access. Provides a data source for `xdg-desktop-portal`'s age verification portal. Does not enforce collection. | [openSUSE Mailing List](https://lists.opensuse.org/archives/list/users@lists.opensuse.org/message/VGSU4EGRW24HWOFEEH4CQF3PKJFF26U7/) |
| **xdg-desktop-portal** | Adding an age verification portal that will consume the systemd `birthDate` field when available. | [9to5Linux](https://9to5linux.com/ubuntu-fedora-linux-mint-eye-age-verification-amid-california-law-backlash) |

---

## Legend

| Icon | Meaning |
|---|---|
| ⚠️ | Reviewing / Leaning toward compliance |
| ❌ | Explicit non-compliance |
| 🚫 | Geo-blocking users from affected regions |
| 🔇 | Silent / No official statement |

---

## Key Laws Referenced

| Law | Jurisdiction | Scope | Effective |
|---|---|---|---|
| AB 1043 (Digital Age Assurance Act) | California, USA | OS providers must collect age at setup, expose bracket API to apps | Jan 1, 2027 |
| ECA Digital (Art. 12) | Brazil | OS and app stores must implement auditable age verification + parental consent for minors | March 17, 2026 |
| Colorado OS Age Attestation Bill | Colorado, USA | Near-identical to AB 1043; open-source exemption amendments proposed | Pending |
| Online Safety Act | United Kingdom | Platforms must deploy age verification; OS not yet explicitly targeted | July 2025 |
| Digital Services Act (DSA) | European Union | Age verification mandates for very large online platforms | Feb 2024 (updated late 2025) |

---

*Last updated: April 2026. Sources: [It's FOSS](https://itsfoss.com/news/distros-response-age-verification-laws/), [9to5Linux](https://9to5linux.com/ubuntu-fedora-linux-mint-eye-age-verification-amid-california-law-backlash), [The Register](https://www.theregister.com/2026/03/13/opinion_os_verification/), [TechRadar](https://www.techradar.com/pro/one-penguin-that-isnt-suitable-for-kids-linux-will-now-carry-out-age-verification-checks), [PC Gamer](https://www.pcgamer.com/software/operating-systems/resistance-to-operating-system-age-checks-coming-from-checks-notes-open-source-calculator-and-an-os-that-may-just-exclude-californians-altogether/), [grigio.org](https://grigio.org/linux-distros-resistance-against-age-verification-laws/)*
