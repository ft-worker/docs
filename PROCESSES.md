- [**Admin Dashboard**](#admin-dashboard)
  - [**Production**](#production)
- [**RN**](#rn)
  - [**Production**](#production-1)
  - [**Staging**](#staging)
  - [**Develop**](#develop)
- [**Seat Map View**](#seat-map-view)
  - [**Production**](#production-2)
  - [**Development**](#development)

# **Admin Dashboard**
## **Production**
- **hotfix/hotfeature/improvement:** directly open branch from `master` branch and open PR into `master`.

***NOTE:*** *For Admin Dashboard there are no other branches to work with.*  
&nbsp;  


# **RN**
## **Production**
- Merging changes into `master` branch only from `staging` branch.
- **hotfix/hotfeature:** directly open branch from `master` branch and open PR into `master`. After, merge `master` branch into `staging` branch and merge `staging` into `develop` branch. This kind of changes must be made if there are some changes in `staging` branch, which can not be merged at that point.

Links:
- Website: https://restlessnites.com
- Dashboard: https://ticketing.restlessnites.com
- Heroku: https://dashboard.heroku.com/apps/restlessnites-production
- GitHub: https://github.com/restlessnites/rn-site


## **Staging**
- Merging changes only from `develop` branch.
- **hotfix/hotfeature:** directly open branch from `staging` branch and open PR into `staging`. After, merge `staging` branch into `develop` branch. This kind of changes must be made if there are some changes in `develop` branch, which can not be merged at that point.

Links:
- Website: https://restlessnit.es
- Dashboard: https://ticketing.restlessnit.es
- Heroku: https://dashboard.heroku.com/apps/restlessnites-staging
- GitHub: https://github.com/restlessnites/rn-site/tree/staging


## **Develop**
- **fix/feature/improvement:** open branch from `develop` branch and after changes done, open PR into `develop` branch.

Links:
- Website: https://preview2.restlessnit.es
- Dashboard: https://ticketing.preview2.restlessnit.es
- Heroku: https://dashboard.heroku.com/apps/restlessnites-development
- GitHub: https://github.com/restlessnites/rn-site/tree/develop

***NOTE:*** *Merge to develop after review and merge develop into staging after testing.*  
&nbsp;  

# **Seat Map View**
## **Production**
- Merging changes only from `dev` branch. Note that after merge `seat-map-view` package's version should be updated according to [npm semantic versioning](https://docs.npmjs.com/about-semantic-versioning). Other steps:
  - Publish new version in [npm](https://www.npmjs.com/).
  - Build `seat-map-view` package:
    - `npm run build`
    - `cd example && npm run build`
  - Send these files to Back-End team members:
    - `/seat-map-view/example/build/static/js/main.js`
    - `/seat-map-view/example/build/static/css/main.css`
  - Open PR in Admin Dashboard with updated `seat-map-view` version and with the same task name/id.

## **Development**
- **fix/feature/improvement:** open branch from `dev` branch and after changes done, open PR into `dev` branch. Note that after merge `seat-map-view` package's version should be updated according to `dev versioning`. Currently we are using `X.Y.Z-beta.{number}` versioning. Other steps:
  - Publish new beta version in [npm](https://www.npmjs.com/).
  - Install new beta version in [seat-map-view-example](https://github.com/ft-worker/seat-map-view-example) for testing.
  - Make sure auto-deployment was successful in [Heroku Dashboard](https://dashboard.heroku.com/apps/seat-map-view).
