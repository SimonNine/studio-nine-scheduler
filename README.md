# Studio Nine scheduler

Runs the social scheduler at studionine.agency every 5 minutes (GitHub Actions, `.github/workflows/social.yml`). Every due LinkedIn and Instagram send in Admin › Social moves one step: create, process, publish.

- **Secret:** `CRON_SECRET` (repo secret), the same value as on Vercel.
- **Keep-alive:** an empty commit on the 1st of each month (`keepalive.yml`). GitHub switches off scheduled workflows after 60 days with no activity.
- **Timing:** GitHub runs these "at least" every 5 minutes. Under load a run can be 10 to 20 minutes late, so a send may go out a little after its time. The site's own daily job is a second safety net.
- **Run it now:** Actions › Social scheduler › Run workflow. Or use **Run it now** on Admin › Social › Accounts & scheduler.
