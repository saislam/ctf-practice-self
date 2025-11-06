# CTF Challenge Solution

## Challenge: Hidden in Plain Sight

### Solution Steps

1. **Read the challenge description** in `CHALLENGE.md`
   - The challenge hints at checking git history

2. **Examine git log**
   ```bash
   git log --all --oneline
   ```
   This shows all commits in the repository.

3. **Check commit messages**
   ```bash
   git log --all --format=fuller
   ```
   Looking at the commit messages reveals that one commit message contains the flag!

4. **Find the flag**
   ```bash
   git show <commit-hash>
   ```
   Or simply read through the commit messages to find:
   ```
   FLAG{g1t_h1st0ry_1s_y0ur_fr13nd}
   ```

### Flag
`FLAG{g1t_h1st0ry_1s_y0ur_fr13nd}`

### Lesson Learned
- Always check git history when analyzing a repository
- Sensitive information can accidentally (or intentionally in CTF challenges) be left in commit messages
- Use `git log`, `git show`, and related commands to explore repository history
- In real-world scenarios, never put sensitive information in commit messages as they are part of the permanent git history

### Additional Exploration Commands
```bash
# View full commit details
git log --all --format=fuller

# Search commit messages (case-insensitive)
git log --all --grep="FLAG" -i

# View specific commit
git show <commit-sha>

# View all changes in a commit
git show <commit-sha> --stat
```
