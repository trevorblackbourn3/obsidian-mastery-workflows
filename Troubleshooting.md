# Appendix E: Troubleshooting Common Issues

**When something breaks, start here.**

**This appendix covers the most common problems and their solutions.**

---

## How to Use This Appendix

1. **Find your problem** in the table of contents below
2. **Try solutions in order** (easiest to hardest)
3. **If problem persists**, see "Getting Help" section
4. **Document your solution** for future reference

---

## Quick Problem Finder

**Performance Issues**
- Obsidian is slow to open
- Lag when typing
- Search is slow
- Dataview queries time out

**Plugin Problems**
- Plugin won't install
- Plugin causes errors
- Plugin conflicts
- Plugin disappeared after update

**Sync Issues**
- Files not syncing across devices
- Sync conflicts
- Lost changes
- Mobile sync problems

**Display Problems**
- Formatting looks wrong
- Images not displaying
- Links broken
- Graph view issues

**File Management**
- Can't find notes
- Attachments missing
- Deleted files won't restore
- Duplicate files appearing

---

## Performance Issues

### Problem: Obsidian is Slow to Open

**Symptoms:** Takes 10+ seconds to open vault.

**Solutions:**

1. **Check vault size:**
   - Settings → About → Vault stats
   - If 10,000+ notes, see Chapter 20 (Scaling)

2. **Disable plugins temporarily:**
   - Settings → Community Plugins → Turn off
   - Restart Obsidian
   - If faster, re-enable plugins one by one to find culprit

3. **Exclude archived folders:**
   - Settings → Files & Links → Excluded files
   - Add `Archive/**` pattern
   - Restart Obsidian

4. **Clear cache:**
   - Close Obsidian
   - Navigate to vault folder
   - Delete `.obsidian/cache` file
   - Restart Obsidian

**[🖼️ IMAGE: troubleshooting-flowchart.png]**

---

### Problem: Lag When Typing

**Symptoms:** Delay between keypress and character appearing.

**Solutions:**

1. **Disable Live Preview:**
   - Settings → Editor → Default editing mode → Source mode
   - Or use Reading view for reference notes

2. **Close unnecessary panes:**
   - Close graph view
   - Close extra split panes
   - Keep only essential sidebars open

3. **Disable intensive plugins:**
   - Temporarily disable:
     - Dataview
     - Calendar
     - Graph-related plugins
   - Test if lag improves

4. **Check file size:**
   - If note is 10,000+ words, split into smaller notes
   - Long notes strain editor

5. **Update Obsidian:**
   - Settings → About → Check for updates
   - Install latest version

**[🖼️ IMAGE: sync-issues-resolution.png]**

---

### Problem: Search is Slow

**Symptoms:** Search takes 5+ seconds to return results.

**Solutions:**

1. **Use more specific search terms:**
   - Instead of "meeting", search "meeting tag:#project-alpha"
   - Narrow results with operators

2. **Exclude folders from search:**
   - Settings → Files & Links → Excluded files
   - Add `Archive/**`, `_Templates/**`

3. **Use Dataview for specific queries:**
   - Instead of full-vault search, query specific folder
   - See Chapter 15 (Dataview)

4. **Reduce vault size:**
   - Archive old notes
   - Delete duplicates
   - Remove unused attachments

---

### Problem: Dataview Queries Time Out

**Symptoms:** Queries don't complete, show error, or take forever.

**Solutions:**

1. **Narrow query scope:**
   ```dataview
   FROM "Projects"  <!-- Specific folder -->
   WHERE status = "active"
   LIMIT 10  <!-- Limit results -->
   ```

2. **Avoid complex calculations:**
   - DataviewJS can be slow
   - Use simpler Dataview query language when possible

3. **Use caching:**
   - Install Buttons plugin
   - Run queries only when needed (button-triggered)

4. **Check for infinite loops:**
   - Especially in DataviewJS
   - Review script logic

**See Chapter 15 and Chapter 20 for optimization details.**

---

## Plugin Problems

### Problem: Plugin Won't Install

**Symptoms:** Error when installing from community plugins.

**Solutions:**

1. **Check internet connection:**
   - Plugin list requires internet to load
   - Verify connection

2. **Disable Safe Mode:**
   - Settings → Community Plugins → Turn off Safe Mode
   - Try installing again

3. **Restart Obsidian:**
   - Close completely
   - Reopen
   - Try installation again

4. **Check for plugin compatibility:**
   - Read plugin description
   - Verify it works with your Obsidian version
   - Settings → About → Current version

5. **Manual installation:**
   - Download plugin from GitHub
   - Extract to `.obsidian/plugins/[plugin-name]/`
   - Enable in Community Plugins

**[🖼️ IMAGE: plugin-conflicts.png]**

---

### Problem: Plugin Causes Errors

**Symptoms:** Error messages, console errors, plugin not working.

**Solutions:**

1. **Update plugin:**
   - Settings → Community Plugins → Check for updates
   - Update problem plugin

2. **Disable and re-enable:**
   - Toggle plugin off
   - Restart Obsidian
   - Toggle plugin back on

3. **Check plugin settings:**
   - Review plugin configuration
   - Reset to defaults if needed

4. **Check console for errors:**
   - View → Toggle Developer Tools (Ctrl+Shift+I / Cmd+Opt+I)
   - Look for error messages in Console tab
   - Report to plugin developer on GitHub

5. **Disable conflicting plugins:**
   - Disable all plugins
   - Re-enable one by one to find conflict

6. **Reinstall plugin:**
   - Uninstall completely
   - Restart Obsidian
   - Reinstall fresh

---

### Problem: Plugin Disappeared After Update

**Symptoms:** Plugin was working, now it's gone from list.

**Solutions:**

1. **Check if plugin was deprecated:**
   - Search for plugin on forum
   - Check if development stopped
   - Look for alternative

2. **Reinstall from Community Plugins:**
   - Settings → Community Plugins → Browse
   - Search for plugin
   - Install again

3. **Check `.obsidian/plugins/` folder:**
   - Close Obsidian
   - Navigate to vault → `.obsidian` → `plugins`
   - See if plugin folder still exists
   - If yes, re-enable in settings
   - If no, reinstall

---

## Sync Issues

### Problem: Files Not Syncing Across Devices

**Symptoms:** Changes on one device don't appear on another.

**Solutions:**

**If using Obsidian Sync:**

1. **Check sync status:**
   - Look for sync icon in bottom-right
   - Click to see sync log
   - Check for errors

2. **Verify settings on both devices:**
   - Settings → Sync → Excluded files
   - Make sure settings match

3. **Force sync:**
   - Settings → Sync → View sync log
   - Click "Sync now"

4. **Check subscription status:**
   - Settings → Sync → Account
   - Verify subscription is active

---

**If using Dropbox/iCloud/Google Drive:**

1. **Check sync app status:**
   - Open Dropbox/iCloud/Google Drive app
   - Verify files are syncing

2. **Verify vault location:**
   - Is vault in synced folder?
   - Check path on both devices

3. **Restart sync service:**
   - Quit Dropbox/iCloud/Google Drive
   - Restart
   - Wait for sync to complete

4. **Check for sync conflicts:**
   - Look for conflicted files in vault
   - Manually resolve conflicts

5. **Force upload:**
   - Modify a file
   - Save
   - Wait for sync indicator

---

### Problem: Sync Conflicts

**Symptoms:** Duplicate files with "conflicted copy" in name.

**Solutions:**

1. **Identify conflicted files:**
   - Search vault for "conflict"
   - Review each file

2. **Manually merge:**
   - Open original file
   - Open conflicted copy
   - Copy any unique content from conflict to original
   - Delete conflicted copy

3. **Prevent future conflicts:**
   - Don't edit same note on multiple devices simultaneously
   - Always sync before and after editing
   - Use Obsidian Sync for better conflict resolution

---

### Problem: Lost Changes

**Symptoms:** Edited note, changes disappeared.

**Solutions:**

1. **Check version history (if using Obsidian Sync):**
   - Right-click note → View version history
   - Restore previous version

2. **Check File Recovery plugin:**
   - Settings → Core Plugins → File Recovery → Enable
   - View snapshots of previous versions

3. **Check cloud service version history:**
   - Dropbox: Right-click file → Version history
   - Google Drive: Right-click file → Manage versions
   - iCloud: Not available

4. **Check local backups:**
   - If using Obsidian Git or backup plugin
   - Restore from backup

**[🖼️ IMAGE: content-issues.png]**

---

## Display Problems

### Problem: Formatting Looks Wrong

**Symptoms:** Markdown not rendering correctly in preview.

**Solutions:**

1. **Toggle edit/preview mode:**
   - Ctrl/Cmd + E
   - Refresh rendering

2. **Check markdown syntax:**
   - See Appendix A for correct syntax
   - Look for unclosed brackets, missing backticks

3. **Disable CSS snippets temporarily:**
   - Settings → Appearance → CSS Snippets
   - Disable all
   - Re-enable one by one to find culprit

4. **Try different theme:**
   - Settings → Appearance → Themes
   - Switch to default theme
   - Test if formatting improves

5. **Clear cache:**
   - Close Obsidian
   - Delete `.obsidian/cache` file
   - Restart

**[🖼️ IMAGE: performance-troubleshooting.png]**

---

### Problem: Images Not Displaying

**Symptoms:** Image links show, but images don't render.

**Solutions:**

1. **Check image path:**
   - Is path correct?
   - Is image in vault?
   - Use `![[image.png]]` not `![](image.png)` for vault images

2. **Check image location:**
   - Settings → Files & Links → Default location for attachments
   - Verify images are in correct folder

3. **Check file extension:**
   - Supported: .png, .jpg, .jpeg, .gif, .svg, .webp
   - Rename if wrong extension

4. **Check file size:**
   - Very large images (10+ MB) may not load
   - Compress image

5. **Reload note:**
   - Close and reopen note
   - Or toggle edit/preview mode

---

### Problem: Links Broken

**Symptoms:** Clicking link shows "File not found".

**Solutions:**

1. **Check if file exists:**
   - Quick switcher (Ctrl/Cmd + O)
   - Search for note
   - If not found, file was deleted or renamed

2. **Update link:**
   - If file renamed, use new name
   - Settings → Files & Links → Automatically update internal links (enable)

3. **Check capitalization:**
   - `[[Note]]` ≠ `[[note]]` on some systems
   - Obsidian is case-sensitive on some platforms

4. **Find broken links:**
   - Install "Broken Links" plugin
   - Or use Dataview:
   ```dataview
   TABLE file.outlinks AS "Broken Links"
   FROM ""
   WHERE any(file.outlinks, (link) => !link.exists)
   ```

5. **Rebuild graph:**
   - Sometimes graph cache is stale
   - Restart Obsidian

---

### Problem: Graph View Shows Nothing

**Symptoms:** Graph view is blank or shows only few notes.

**Solutions:**

1. **Check filters:**
   - Right sidebar in graph view → Filters
   - Make sure filters aren't excluding all notes

2. **Zoom out:**
   - Scroll to zoom in/out
   - Notes might be clustered far away

3. **Check if notes are linked:**
   - Graph only shows linked notes
   - Unlinked notes don't appear (unless setting changed)

4. **Enable orphans:**
   - Graph settings → Display
   - Check "Show orphans"

5. **Rebuild graph:**
   - Close and reopen graph view
   - Or restart Obsidian

**[🖼️ IMAGE: Graph view troubleshooting]**

---

## File Management Problems

### Problem: Can't Find Note

**Symptoms:** Know note exists, can't locate it.

**Solutions:**

1. **Use Quick Switcher:**
   - Ctrl/Cmd + O
   - Start typing note name
   - Fuzzy search finds it

2. **Use search:**
   - Ctrl/Cmd + Shift + F
   - Search unique phrase from note

3. **Check recently modified:**
   - File explorer → Sort by modified date
   - Look at recent files

4. **Check specific folder:**
   - File explorer → Navigate folders
   - Might be misfiled

5. **Search by tag:**
   - Tag pane → Click relevant tag
   - See all notes with that tag

**[🖼️ IMAGE: Finding lost notes]**

---

### Problem: Attachments Missing

**Symptoms:** Images, PDFs, or other attachments gone.

**Solutions:**

1. **Check attachments folder:**
   - Settings → Files & Links → Default attachment location
   - Navigate to that folder
   - Look for files

2. **Search vault for file type:**
   - Quick Switcher → Type `.png` or `.pdf`
   - Shows all files of that type

3. **Check if accidentally deleted:**
   - Settings → Core Plugins → File Recovery
   - Check for deleted attachments

4. **Restore from backup:**
   - Cloud sync version history
   - Local backup
   - Git history (if using Obsidian Git)

**[🖼️ IMAGE: Attachment recovery]**

---

### Problem: Deleted Files Won't Restore

**Symptoms:** Tried to restore, file doesn't appear.

**Solutions:**

1. **Check system trash:**
   - Settings → Files & Links → Deleted files
   - If set to "System trash", check OS trash/recycle bin
   - Restore from there

2. **Check Obsidian trash:**
   - If set to ".trash folder"
   - Navigate to `.trash` folder in vault
   - Move file back manually

3. **Use File Recovery plugin:**
   - Settings → Core Plugins → File Recovery → Enable
   - View deleted files
   - Restore

4. **Restore from backup:**
   - Cloud service version history
   - Local backup
   - Git history

**[🖼️ IMAGE: File restoration steps]**

---

## Mobile-Specific Issues

### Problem: Mobile App Won't Sync

**Symptoms:** Changes on mobile don't appear on desktop (or vice versa).

**Solutions:**

1. **Check mobile internet:**
   - Verify WiFi or cellular connection
   - Try opening browser to confirm

2. **Force sync:**
   - Pull down on note list to refresh
   - Or open Settings → Sync → Sync now

3. **Check sync settings:**
   - Verify same account on mobile and desktop
   - Check excluded folders match

4. **Reinstall mobile app:**
   - Uninstall Obsidian mobile
   - Reinstall from App Store/Play Store
   - Sign back in

**[🖼️ IMAGE: Mobile sync troubleshooting]**

---

### Problem: Plugins Not Working on Mobile

**Symptoms:** Plugin works on desktop, not mobile.

**Solutions:**

1. **Check plugin compatibility:**
   - Not all plugins support mobile
   - Read plugin description

2. **Enable on mobile:**
   - Mobile Settings → Community Plugins
   - Make sure plugin is enabled

3. **Use mobile-friendly alternative:**
   - See Chapter 7 for mobile-friendly setups
   - Design manual fallback (no Dataview queries, etc.)

**[🖼️ IMAGE: Mobile plugin compatibility]**

---

## Configuration Issues

### Problem: Settings Not Saving

**Symptoms:** Change settings, they revert after restart.

**Solutions:**

1. **Check file permissions:**
   - Ensure vault folder is writable
   - Not on read-only drive

2. **Check sync:**
   - Settings sync across devices
   - Might be overwritten by other device's settings

3. **Disable settings sync temporarily:**
   - Settings → Sync → Sync settings (disable)
   - Configure on one device first
   - Re-enable after

4. **Manually edit config:**
   - Close Obsidian
   - Navigate to `.obsidian/app.json`
   - Edit settings directly
   - Restart Obsidian

**[🖼️ IMAGE: Settings configuration]**

---

### Problem: Hotkeys Not Working

**Symptoms:** Keyboard shortcuts don't trigger commands.

**Solutions:**

1. **Check for conflicts:**
   - Settings → Hotkeys
   - Filter by shortcut
   - Look for conflicts

2. **Reassign hotkey:**
   - Delete existing assignment
   - Assign new shortcut
   - Test

3. **Check OS overrides:**
   - System shortcuts override Obsidian
   - Example: Cmd+H hides app on Mac
   - Choose different shortcut

4. **Restart Obsidian:**
   - Sometimes hotkeys don't register until restart

**[🖼️ IMAGE: Hotkey troubleshooting]**

---

## Getting Help When Stuck

**If this appendix doesn't solve your problem:**

### 1. Search Obsidian Forum

**URL:** `forum.obsidian.md`

- Use search function
- Look for similar issues
- Solutions often already posted

---

### 2. Check GitHub Issues (for plugins)

**Find plugin on GitHub:**
- Search "[plugin name] obsidian github"
- Check Issues tab
- See if bug already reported

---

### 3. Ask in Discord

**Join:** `discord.gg/obsidianmd`

**Channels:**
- `#help` - General help
- `#mobile` - Mobile issues
- `#appearance` - CSS/theme issues
- `#plugins` - Plugin-specific

**When asking, include:**
- Obsidian version
- OS and version
- Steps to reproduce
- Screenshots (if relevant)
- What you've already tried

---

### 4. Post on Forum

**Create detailed post:**

**Title:** Clear description ("Dataview queries timing out in large vault")

**Body:**
- Obsidian version
- Operating system
- Plugins installed
- Steps to reproduce
- Expected vs actual behavior
- What you've tried
- Screenshots/error messages

---

### 5. Developer Tools

**Access console:**
- View → Toggle Developer Tools
- Or: Ctrl+Shift+I (Windows/Linux) / Cmd+Opt+I (Mac)

**Console tab shows:**
- JavaScript errors
- Plugin errors
- Warnings

**Copy error messages when asking for help.**

**[🖼️ IMAGE: Developer tools console]**

---

## Prevention: Avoiding Common Issues

**Best practices to prevent problems:**

1. **Regular backups:**
   - 3-2-1 backup strategy (Chapter 20)
   - Test restores quarterly

2. **Update cautiously:**
   - Read release notes before updating
   - Update one thing at a time
   - Update plugins after Obsidian core

3. **Limit plugins:**
   - Only install what you need
   - Disable unused plugins
   - Audit quarterly

4. **Monitor performance:**
   - Track startup time
   - Note when things slow down
   - Address issues early

5. **Document your setup:**
   - List installed plugins
   - Note custom settings
   - Makes troubleshooting easier

**[🖼️ IMAGE: Prevention checklist]**

---

## Emergency: Vault Corruption

**If vault becomes completely unusable:**

### Nuclear Option: Clean Reinstall

1. **Backup vault first** (copy entire folder)
2. **Export important notes** (just in case)
3. **Close Obsidian**
4. **Delete `.obsidian` folder** (this removes all settings/plugins)
5. **Restart Obsidian**
6. **Vault opens fresh with default settings**
7. **Reinstall plugins one by one**
8. **Reconfigure settings**

**This solves 99% of corruption issues.**

**[🖼️ IMAGE: Clean reinstall process]**

---

**Most problems have simple solutions.**

**Try obvious fixes first: restart, update, disable plugins.**

**Document solutions you discover for future reference.**

**When in doubt, ask the community. They've seen it before.**
