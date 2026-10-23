# Mac 游戏库可玩性顾问｜Mac Game Library Advisor

Mac 上想玩 Windows 游戏，先别急着装兼容工具，先看这份清单。

Steam 库躺着一堆 Windows 游戏，Mac 用户常见的做法是先装个 Whisky 再一个个试，试到第四个发现卡在反作弊上，前面折腾的时间全白费。这个 skill 反过来做：先把库过一遍，哪些原生能跑、哪些靠 Whisky 和 GPTK 能跑且跑得动、哪些根本别想，一次说清楚，再决定要不要动手。

Your Steam library is full of Windows games and you're on a Mac. The usual move is to install a compatibility layer and start guessing game by game — until one hits kernel-level anti-cheat and the whole afternoon is gone. This skill goes the other way around: sweep the library first, sort every title into native / runs well under Whisky + GPTK / not viable / not enough data, then decide whether it's worth setting anything up.

## 能力范围 / Capabilities

- **可玩性四分类**：Mac 原生、无原生但兼容效果好、兼容效果差或不可行、资料不足（标注"需实机验证"）。原生和需要兼容的分开列，不混在一张表里
- **运行效果分级**：流畅 / 基本可玩 / 勉强能跑 / 不可行。判断依据是玩家在具体机型上的实际帧率和反馈，不是"安装难不难"
- **Mod 可用性**：可用 / 部分可用 / 不可用。看的是 BepInEx、r2modman、创意工坊这些框架在兼容层下能不能跑起来，DLL 注入和 Script Extender 这类通常要单独确认
- **反作弊与启动器风险**：Easy Anti-Cheat、BattlEye、Vanguard、Ricochet 是否有 Mac 豁免；Rockstar Launcher、Ubisoft Connect、EA App 这类第三方启动器会不会拖后腿
- **相似游戏推荐**：按游玩时长和最近游玩反推偏好（不是按拥有数量），只推库里没有的、特别好评以上的、Mac 上跑得动的，并说明具体像你库里哪一款
- **安装配置**：确认之后直接协助配置 Whisky / GPTK、装 Mod、处理存档路径差异

- **Four-way playability sort**: native macOS, no native build but runs well, poor or not viable, insufficient data (flagged as "needs a real-hardware test"). Native and compatibility-dependent titles never share a table
- **Performance grading**: smooth / playable / barely runs / not viable — based on reported framerates on specific Mac models, not on how hard the setup is
- **Mod availability**: works / partially works / doesn't. Whether BepInEx, r2modman or Workshop frameworks survive the compatibility layer; DLL injection and Script Extenders usually need a separate look
- **Anti-cheat and launcher risk**: whether Easy Anti-Cheat, BattlEye, Vanguard or Ricochet has a Mac exemption, and whether a Rockstar / Ubisoft / EA launcher gets in the way
- **Similar game picks**: preferences inferred from playtime and recent activity rather than library size, recommending only titles you don't own, rated Very Positive or above, and actually playable on a Mac
- **Setup help**: once you say go, it walks through Whisky / GPTK configuration, mod installs, and the save-path differences

## 两条硬规则 / Two Hard Rules

**每次都现搜，不吃老本。** Mac 游戏兼容性变得比攻略还快，半年前的结论经常已经过期。每次检查都重新搜 Steam 商店页、AppleGamingWiki、Whisky 社区、PCGamingWiki、ProtonDB，以及 GitHub、Reddit、B 站、YouTube 上的近期实测，不依赖任何内置名单。

**只推免费方案。** Whisky、GPTK、串流都是免费的，默认只在这几条路里选。CrossOver、Parallels 这类付费方案，你不问就不提。

**Always search fresh, never from memory.** Mac compatibility rots faster than a walkthrough. Every check re-searches the Steam store page, AppleGamingWiki, the Whisky community, PCGamingWiki, ProtonDB, plus recent hands-on reports from GitHub, Reddit, Bilibili and YouTube. There is no built-in list of "known good" games.

**Free options only.** Whisky, GPTK and game streaming are the default menu. Paid tools like CrossOver or Parallels come up only if you ask about them.

## 装到哪里 / Installation

### Claude Code

```bash
git clone https://github.com/ruodou233/mac-game-library-advisor.git ~/.claude/skills/mac-game-library-advisor
```

### WorkBuddy / 其它支持 skills 目录的 Agent

```bash
git clone https://github.com/ruodou233/mac-game-library-advisor.git ~/.workbuddy/skills/mac-game-library-advisor
```

或者手动把 `SKILL.md` 放进对应 skill 目录，让 `mac-game-library-advisor/` 下直接就是 `SKILL.md`。

Or copy `SKILL.md` into your agent's skills directory so that `mac-game-library-advisor/SKILL.md` exists.

### 直接解压 .skill 包

[`dist/mac-game-library-advisor.skill`](dist/mac-game-library-advisor.skill) 是 zip 格式，改扩展名后解压即可，包内路径为 `mac-game-library-advisor/SKILL.md`：

```bash
unzip dist/mac-game-library-advisor.skill -d ~/.claude/skills/
```

The `.skill` file is a plain zip with `mac-game-library-advisor/SKILL.md` inside. Rename to `.zip` and extract, or use the command above.

## 隐私 / Privacy

Skill 里不含 Steam ID、登录状态、Cookie 或浏览器路径。需要登录 Steam 时让用户在自己的浏览器里操作，不要密码、不要验证码、不要令牌。可以直接转发给别人。

No Steam ID, session state, cookies or browser paths are baked in. Anything requiring a Steam login happens in your own browser — no passwords, codes or tokens over the chat. Safe to hand to someone else.

## License

MIT. 兼容信息来自公开社区，仅供参考，实际体验以你自己机器上的结果为准。

MIT. Compatibility notes come from public community sources and are informational only — what actually happens on your machine is the final word.
