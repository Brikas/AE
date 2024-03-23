- My custom CSS
	- ```css
	  /* 2024-03-23 */
	  .custom-query-page-result .breadcrumb {
	    font-size: x-small
	  }
	  
	  /* Alternative embed breadcrumbs */
	  div[data-ref=logseq-another-embed] {
	      font-size: x-small;
	    	opacity: 50%;
	  }
	  
	  /* Embed background colors */
	  .dark .color-level {
	    background-color: var(--lx-gray-02,var(--color-level-1,var(--rx-gray-02)))
	  }
	  
	  html[data-theme=light] .color-level:not(.sidebar-item) {
	    background-color: var(--lx-gray-02-alpha,var(--color-level-1,var(--lx-gray-03-alpha)))
	  }
	  
	  .dark ::selection {
	      background: var(--lx-gray-08-alpha);
	  }
	  
	  .light-theme, .white-theme, html[data-theme=light] {
	    --ls-highlight-color-pink: var(--color-pink-400);
	    --ls-highlight-color-green: var(--color-green-400);
	    --ls-highlight-color-blue: var(--color-blue-400);
	    --ls-highlight-color-red: var(--color-red-400);
	    --ls-highlight-color-purple: var(--color-purple-400);
	    --ls-highlight-color-yellow: var(--color-yellow-500);
	    --ls-highlight-color-gray: var(--color-gray-300);
	  }
	  
	  /* Remove line break after {r } {g } etc. */
	  .macro,
	  .macro .hiccup_html,
	  .macro .raw_html {
	      display: inline;
	  }
	  ```