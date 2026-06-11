# Release checklist

Every portal release, in this order.

- [ ] Changelog merged and the version bumped
- [ ] Staging deploy green for 24 hours
- [ ] Database migrations reviewed by a second engineer
- [ ] Static assets uploaded and the CDN cache purged
- [ ] Support told the release window

Roll back by redeploying the previous tag; never hotfix in production.
