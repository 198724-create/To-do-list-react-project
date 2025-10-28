# To-do-list-react-project
React Project
// Global app state (Redux or Context)
{
  auth: {
    isLoggedIn: false,
    user: null            // { id, name, email } if you add auth later
  },

  search: {
    query: "",            // current search string
    filters: {            // UI-level filters
      rating: "g",        // "y" | "g" | "pg" | "pg-13" | "r" (or "any")
      sort: "relevance"   // "relevance" | "recent" | "trending"
    },
    results: [            // normalized is fine too; array is okay for MVP
      // {
      //   id: "abc123",
      //   title: "dancing cat",
      //   url: "https://media.giphy.com/...",
      //   previewUrl: "https://media.giphy.com/.../200w.gif",
      //   rating: "pg",
      //   tags: ["cat", "dance"]
      // }
    ],
    pagination: {
      page: 1,            // 1-based page index for UI
      pageSize: 24,       // items per page
      total: 0,           // total hits from API
      offset: 0           // raw Giphy API offset
    },
    status: "idle",       // "idle" | "loading" | "succeeded" | "failed"
    error: null
  },

  favorites: {
    ids: [],              // ["abc123", "def456"]
    entities: {           // id → GIF object (same shape as in results)
      // "abc123": { ... }
    }
  },

  ui: {
    detailModalOpen: false,
    detailGifId: null,    // which GIF is shown in the modal (if any)
    toast: null,          // { type: "success" | "error", message: string } or null

    // contact form network flags only (the fields live in ContactForm local state)
    contact: {
      sending: false,
      sent: false,
      error: null
    }
  }
}
