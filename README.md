# Nathan & Piper's wedding website

Autumn colors, the couple's photographs, wedding details, and an embedded Google RSVP form.

- Wedding: October 24, 2026, at 4 PM Eastern
- Ceremony and reception: 1166 County Road 147, Romulus, NY
- RSVP deadline: October 12, 2026
- Intended domain: https://rodriguez-wedding.com
- Source: https://github.com/hoferjoshuamikel-netizen/rodriguez-wedding

## RSVPs

The RSVP section embeds the Google Form supplied by Joshua. A fallback button opens the same form in a new tab. Responses are collected in Google Forms, not in this public repository or Vercel.

[Open the respondent form](https://docs.google.com/forms/d/e/1FAIpQLSdkV5kygCf9mJ3Enhk6XfMZ78OeXjCNgTAuRu2wT9WPxOMxmQ/viewform)

In the form owner's Google account, open the form in edit mode and select **Responses**. Select **Link to Sheets** to keep a spreadsheet. The three-dot menu in Responses offers **Get email notifications for new responses**.

Before inviting guests, open the live site in a private browser window. Make one clearly labeled test submission and confirm that it appears in Responses. Keep any response spreadsheet private.

The guest photo upload destination is still pending. In site.config.js, set photoShare.url to the OneDrive file-request link and photoShare.enabled to true when the link is ready.

## Deploy on the free Vercel Hobby plan

This static HTML/CSS/JavaScript site needs no database, custom login, npm dependencies, API keys, or environment variables.

1. Open https://vercel.com/new and sign in using the GitHub account that owns this repository.
2. Select the free **Hobby** account/workspace for this personal wedding project.
3. Import **hoferjoshuamikel-netizen/rodriguez-wedding**. If missing, configure the Vercel GitHub app to allow this repository, then refresh.
4. The included vercel.json supplies the static-site settings. Check:

| Setting | Value |
| --- | --- |
| Project name | rodriguez-wedding |
| Framework Preset | Other |
| Root Directory | ./ |
| Build Command | Empty (override enabled if needed) |
| Output Directory | . |
| Environment Variables | None |

5. Click **Deploy**. Open the actual .vercel.app address Vercel gives you.
6. Test desktop/mobile layout, RSVP embed, its new-tab fallback, and directions. Use a private browser window to verify guests are not blocked by Vercel Authentication.

## Connect the domain while preserving Microsoft email

1. In Vercel, open **Project Settings > Domains**.
2. Add **rodriguez-wedding.com** and **www.rodriguez-wedding.com**. Serve the site on the main domain and explicitly redirect www to it.
3. Open the current DNS provider's records page. DNS checked September 30, 2026 used ns35.domaincontrol.com and ns36.domaincontrol.com (GoDaddy). Save a screenshot of the current records.
4. Copy the **exact records displayed by Vercel**. The main domain normally uses an A record named @ and www uses a CNAME. Use this project's displayed values.
5. Update only the website's DNS records. Keep nameservers and Microsoft email records: MX, SPF/TXT, DKIM, DMARC, autodiscover, and other mail/verification entries. Resolve conflicts only for the website hostnames being changed.
6. Wait for valid configuration in Vercel, then test HTTPS at both names and the www redirect.

The initial DNS snapshot had two root A values, 15.197.148.33 and 3.33.130.190, and Microsoft MX rodriguezwedding-com02c.mail.protection.outlook.com. Recheck current records before editing; the snapshot is not a command to delete records blindly.

Do not purchase or transfer the domain again. This setup uses Vercel Hobby within its free limits. Existing domain/email renewals remain separate.

## Future edits

Wedding details and links: site.config.js. Layout: index.html. Styles: styles.css. Interactivity: script.js. Photos: assets/photos/.

Once Vercel is connected, commits to main redeploy automatically.

## Documentation

- [Vercel Hobby plan](https://vercel.com/docs/plans/hobby)
- [Static build settings](https://vercel.com/docs/builds/configure-a-build)
- [Import a Git repository](https://vercel.com/docs/git)
- [Configure a custom domain](https://vercel.com/docs/domains/working-with-domains/add-a-domain)
- [Google Forms response management](https://support.google.com/docs/answer/139706)
