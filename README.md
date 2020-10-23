# WordPress Theme Review Test

This project will run E2E tests on a theme in preparation for the WordPress.org theme review. This project only triggers an GitHub action that runs the test.

## To trigger the actions on GitHub

1. Generate a personal token in Settings > Developer Settings > Personal Access Tokens
2. Use the token to trigger a github action via API (replace the `{account}/{repo}` with your fork):

	curl -H "Authorization: token $GITHUB_PERSONAL_TOKEN" -H 'Accept: application/vnd.github.everest-preview+json' "https://api.github.com/repos/{account}/{repo}/dispatches" -d '{"event_type": "Test Theme", "client_payload": {"theme_slug": "twentytwenty", "theme_zip": "https://downloads.wordpress.org/theme/twentytwenty.1.5.zip", "accessible_ready": "true" }}'

3. The result will appear in the "Actions" section of this repo.
