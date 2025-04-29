# goauth - Simple and Easy-to-Use Go Third-Party Login SDK

[![Go Reference](https://pkg.go.dev/badge/github.com/OmniStoneX/goauth.svg)](https://pkg.go.dev/github.com/OmniStoneX/goauth)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
![Under Active Development](https://img.shields.io/badge/Status-Under%20Active%20Development-blue)

[简体中文](README_zh-CN.md) | **English**

**goauth** is a lightweight, easy-to-integrate, and extensible Go SDK designed to help you quickly implement third-party login functionality based on the OAuth 2.0 protocol. It currently supports Google Sign-In, WeChat Login, and GitHub Login, with ongoing integration of more popular third-party login platforms.

## Features

* **Simple and Easy to Use:** Provides clear and straightforward APIs for easy integration into your Go web applications or services.
* **Multi-Platform Support:**
  * ✅ **Google Sign-In:** Quickly integrate Google Sign-In for a seamless user experience.
  * ✅ **WeChat Login:** Supports both QR code login and web authorization login.
  * ✅ **GitHub Sign-In:** Integrates the GitHub OAuth authorization flow.
  * ⏳ **Under Active Development:** We are actively adding support for more platforms. Stay tuned!
* **Flexible Configuration:** Allows for flexible configuration based on the requirements of different platforms.
* **Clear Error Handling:** Provides detailed error information for easy debugging.
* **Lightweight Dependencies:** Minimizes external dependencies to keep the SDK lightweight.

## Getting Started

### Installation

Install the goauth SDK using the `go get` command:

```bash
go get [github.com/OmniStoneX/goauth](https://github.com/OmniStoneX/goauth)
```

### Usage Example

```go
// Add your English example code here
package main

import (
	"fmt"
	"net/http"

	"[github.com/OmniStoneX/goauth/oauth](https://github.com/OmniStoneX/goauth/oauth)"
	"[github.com/OmniStoneX/goauth/providers/google](https://github.com/OmniStoneX/goauth/providers/google)"
)

func googleLoginHandler(w http.ResponseWriter, r *http.Request) {
	// Configure Google OAuth
	config := &google.Config{
		ClientID:     "YOUR_GOOGLE_CLIENT_ID",
		ClientSecret: "YOUR_GOOGLE_CLIENT_SECRET",
		RedirectURL:  "YOUR_GOOGLE_REDIRECT_URL",
		Scopes:       []string{"profile", "email"}, // Your required Google Scopes
	}

	// Initialize Google Provider
	provider, err := google.New(config)
	if err != nil {
		http.Error(w, fmt.Sprintf("Failed to initialize Google provider: %v", err), http.StatusInternalServerError)
		return
	}

	// Handle Google login request
	authCode := r.URL.Query().Get("code")
	if authCode == "" {
		// User not authorized, redirect to Google authorization page
		authURL := provider.AuthCodeURL("state-nonce") // state-nonce for preventing CSRF attacks
		http.Redirect(w, r, authURL, http.StatusFound)
		return
	}

	// Get user information using the authorization code
	userInfo, err := provider.GetUserInfo(r.Context(), authCode)
	if err != nil {
		http.Error(w, fmt.Sprintf("Failed to get user info from Google: %v", err), http.StatusInternalServerError)
		return
	}

	fmt.Fprintf(w, "Google User Info: %+v\n", userInfo)
	// Process your user login logic here
}

func main() {
	http.HandleFunc("/auth/google/login", googleLoginHandler)
	fmt.Println("Server started on :8080")
	http.ListenAndServe(":8080", nil)
}
```

### Other Platform Integration

Please refer to the following documentation:

* [Google Sign-In](docs/google.md)
* [WeChat Login](docs/wechat.md)
* [GitHub Login](docs/github.md)
* [Weibo Login](docs/weibo.md)

### Platforms Under Active Development

* [X (formerly Twitter)](Link to the platform's developer documentation or your Issue)
* [QQ](Link to the platform's developer documentation or your Issue)
* ...

### Configuration

Refer to the specific documentation for each platform.

### Contributing

Contributions of any kind are welcome\! If you find a bug or wish to add new features or platform support, please feel free to submit Issues or Pull Requests.

### License

[MIT](LICENSE)

### Contact

[Your contact information, e.g., GitHub Issues or email]