# cd14715-claude-code-classroom

Course repo for Claude Code, the Claude API and the Claude Agent SDK. Lessons 00-13 plus a capstone in `project/`.
Most lessons have `demo/`, `exercise/starter/` and `exercise/solution/`.

## Layout
- Lesson 00 (warm-up) is Python (`test.py`) plus a standalone TypeScript script (`hello-agent.ts`).
- Lessons 01, 02 and 05-12, and `project/starter`, are npm workspaces listed in the root `package.json`. Run `npm install` at the repo root for these.
- Lessons 00, 03, 04 and 13 are NOT in the root workspaces list. Install inside their own folder (`cd lesson-00-warm-up/exercise/starter && npm install`).
- Lessons are TypeScript. Run scripts with `npx tsx <file>` or `npm start` in the lesson folder.

## Environment (Windows + Git Bash)
- Required versions: Node v22.4.1, tsx 4.23.15.
- Secrets and config live in a gitignored `.env` at the repo root: `ANTHROPIC_API_KEY`, `ANTHROPIC_BASE_URL=https://claude.vocareum.com`, `ANTHROPIC_MODEL`.
- Never put the API key in tracked files, notes or chat.
- `.env` lines must be `KEY=value` with no spaces around `=`, or bash cannot source it.
- Load it into the shell with `set -a; source .env; set +a` (from the repo root).
- Python's `load_dotenv()` finds a root `.env` from subfolders. The npm `dotenv/config` only reads `.env` in the current working directory, so copy `.env` into the lesson folder or source it into the shell first.
- Agent SDK scripts on Windows need `CLAUDE_CODE_GIT_BASH_PATH` set to the Git Bash binary, otherwise Claude Code exits with code 1. Set it in `~/.bashrc`.
- If `node` is not found in Git Bash, add `/c/Program Files/nodejs` to `PATH` in `~/.bashrc`.
- The repo path contains spaces and a comma (`Adastra, s.r.o`), so always quote paths.

## Conventions
- Keep exercise `starter/` and `solution/` folders in sync with their READMEs.
- Do not commit `.env`, `node_modules` or secrets.
