# How to Contribute to the EP11 Developer Blog & Wiki

We welcome community members and IBM developers to contribute blog posts, technical deep-dives, and tutorials!

---

### Authoring a New Blog Post

1. **Create your post file** in the `wiki/` directory using the naming convention:
   ```text
   wiki/YYYY-MM-DD-your-article-slug.md
   ```
2. **Add the post header**:
   ```markdown
   # Your Article Title

   *Author: Your Name / Squad*  
   *Published: YYYY-MM-DD*  
   *Tags: `Tag1`, `Tag2`*

   ---
   ```
3. **Update the Index**:
   * Add a summary card to [`wiki/Home.md`](wiki/Home.md) under **Featured & Latest Articles**.
   * Add your article title to the **Recent Posts** list in [`wiki/_Sidebar.md`](wiki/_Sidebar.md).
4. **Submit a Pull Request**:
   * Open a PR following the [Contributing Guidelines](../Contributing.md) with DCO sign-off (`git commit -s`).
