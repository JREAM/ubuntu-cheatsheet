## Do Not Search Index Folders

**@TODO: This is not fully correct, need help**
There is not a very compelling reason to have Gn
ome index PHP's `/vendor` folder nor Nodes `node_modules`
folder. It convolutes things and takes up space.

To customize, press <kbd>SUPER</kbd> and search for `dconf`, open `dconf-editor`. Press `CTRL+L` to focus on the
location and go here (you can copy paste): `/org/freedesktop/tracker/miner/files/ignored-directories-with-content`

- Untick `Use Default Value`
- In `Custom Value`, append the following, here is my full text:
  - `['.trackerignore', '.git', '.hg', 'node_modules', 'vendor']`
- In the Terminal type the following:
  - `tracker status` to see how much space is used to index.
  - `tracker index -f .` to re-index
  - I am uncertain, but I would also update internal database for searching, type: `sudo updatedb`
  - Lastly, you can type `tracker status` again

If you notice, `.trackerignore` can be placed in any folder, and the tracker (or file indexer) will ignore that
individual folder as well. This is a global way to do it and it's easier.
