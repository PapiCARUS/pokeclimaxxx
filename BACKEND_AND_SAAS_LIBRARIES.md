# Backend and SaaS Libraries Research

Date : 2026-07-11.

## Contexte technique

Backend actuel : Node.js HTTP natif. Objectif futur : PostgreSQL, SaaS multi-utilisateur, authentification, isolation des données. Cette étude ne recommande pas automatiquement une migration vers Express/Nest/Fastify ; elle privilégie les options intégrables progressivement.

## PostgreSQL

### node-postgres / pg

- Sources : https://node-postgres.com/ et https://github.com/brianc/node-postgres
- Rôle : client PostgreSQL bas niveau pour Node.js.
- Faits : supporte pooling, requêtes paramétrées, prepared statements, cursors, streaming, LISTEN/NOTIFY, COPY.
- Maturité : très mature ; npm indique une publication récente en 2026 pour `pg`.
- Avantages : compatible Node natif, pas d’architecture imposée, contrôle SQL complet.
- Inconvénients : moins de type-safety, plus de code SQL manuel.
- Recommandation : utiliser comme première brique PostgreSQL.

### Kysely

- Sources : https://kysely.dev/ et https://github.com/kysely-org/kysely/releases
- Rôle : query builder SQL type-safe.
- Faits : dialectes PostgreSQL/MySQL/MSSQL/SQLite/PGlite ; releases récentes visibles.
- Avantages : SQL contrôlé, type-safety, moins lourd qu’un ORM.
- Inconvénients : bénéfice maximal avec TypeScript ; ajout de complexité.
- Compatibilité : bonne si le projet migre vers TS ou accepte types JSDoc/étape progressive.
- Recommandation : tester après stabilisation du schéma ; ne pas bloquer la migration initiale dessus.

### Drizzle ORM

- Sources : https://orm.drizzle.team/ et https://github.com/drizzle-team/drizzle-orm
- Rôle : ORM/query builder TypeScript léger.
- Faits : activité forte ; releases v1.0 beta/rc visibles, changelog mentionnant risques de breaking changes.
- Avantages : schéma typé, migrations, SQL proche.
- Inconvénients : écosystème en évolution ; nécessite TypeScript pour plein intérêt.
- Recommandation : tester, mais éviter comme fondation unique tant que la bêta doit rester simple.

## Migrations

### node-pg-migrate

- Sources : https://salsita.github.io/node-pg-migrate/ et https://github.com/salsita/node-pg-migrate
- Rôle : migrations PostgreSQL Node.js.
- Faits : CLI up/down, migrations JS/SQL, activité récente v9 alpha.
- Avantages : spécialisé PostgreSQL, compatible backend Node existant.
- Inconvénients : attention aux versions alpha ; choisir stable.
- Recommandation : utiliser une version stable pour migrations SQL.

### dbmate

- Source : https://github.com/amacneil/dbmate
- Rôle : migrations SQL simples, outil externe.
- Avantages : fichiers SQL purs, indépendant du framework.
- Inconvénients : dépendance binaire/outillage séparé.
- Recommandation : tester si l’équipe préfère SQL pur.

## Validation d’API

### Zod

- Source : https://zod.dev/
- Rôle : validation schémas JS/TS.
- Avantages : simple, utilisable côté API, imports, formulaires.
- Inconvénients : type-safety complète avec TS.
- Recommandation : utiliser pour entrées HTTP et migration JSON.

### Valibot

- Source : https://valibot.dev/
- Rôle : validation légère.
- Avantages : léger, moderne.
- Inconvénients : moins standard que Zod.
- Recommandation : tester si bundle/poids devient critique.

## Sessions / Auth

### Session serveur maison + pg

- Rôle : table `auth_sessions`, cookie HTTP-only, token hashé.
- Avantages : révocation simple, intégration Node natif, contrôle tenant.
- Inconvénients : il faut implémenter correctement expiration, CSRF, cookies secure.
- Recommandation : utiliser pour bêta privée si l’équipe reste en Node HTTP natif.

### Lucia Auth

- Note : Lucia a historiquement changé de statut/positionnement ; vérifier avant adoption.
- Recommandation : éviter adoption automatique ; lire l’état actuel avant décision.

### Better Auth

- Source : https://www.better-auth.com/
- Rôle : auth TypeScript moderne.
- Avantages : fonctionnalités SaaS modernes.
- Inconvénients : peut imposer structure ; à vérifier avec backend natif.
- Recommandation : tester seulement si migration architecture acceptée.

### Auth.js

- Source : https://authjs.dev/
- Rôle : auth web, surtout frameworks modernes.
- Avantages : providers OAuth.
- Inconvénients : plus adapté Next/SvelteKit/etc. qu’un serveur HTTP natif.
- Recommandation : éviter pour bêta Node natif sauf migration frontend/backend.

## Email transactionnel

### Resend

- Source : https://resend.com/docs
- Rôle : emails transactionnels développeur-friendly.
- Avantages : API simple, templates React possibles.
- Inconvénients : service externe.
- Recommandation : tester pour invitations/reset plus tard.

### Postmark

- Source : https://postmarkapp.com/developer
- Rôle : email transactionnel fiable.
- Avantages : réputation forte sur délivrabilité.
- Inconvénients : coût.
- Recommandation : utiliser si emails critiques.

## Logs

### Pino

- Source : https://getpino.io/
- Rôle : logger JSON performant.
- Avantages : rapide, standard Node.
- Inconvénients : nécessite conventions de champs.
- Recommandation : utiliser.

### Winston

- Source : https://github.com/winstonjs/winston
- Rôle : logger flexible.
- Avantages : mature.
- Inconvénients : plus lourd.
- Recommandation : tester seulement si besoin de transports complexes.

## Rate limiting

### rate-limiter-flexible

- Source : https://github.com/animir/node-rate-limiter-flexible
- Rôle : rate limiting Node avec backends mémoire/Redis/etc.
- Avantages : flexible.
- Inconvénients : Redis utile en production multi-instance.
- Recommandation : utiliser/tester pour login et API sensibles.

### express-rate-limit

- Rôle : rate limiting Express.
- Recommandation : éviter tant que le backend n’est pas Express.

## Stockage fichiers

### S3 compatible storage

- Options : AWS S3, Cloudflare R2, Backblaze B2, MinIO.
- Recommandation : utiliser une abstraction S3 compatible pour images cartes, exports, imports.

### @aws-sdk/client-s3

- Source : https://docs.aws.amazon.com/AWSJavaScriptSDK/v3/latest/client/s3/
- Avantages : officiel, compatible S3.
- Inconvénients : SDK modulaire mais verbeux.
- Recommandation : utiliser pour stockage futur.

## Sauvegardes

### pg_dump / pg_restore

- Source : https://www.postgresql.org/docs/current/app-pgdump.html
- Rôle : sauvegarde/restauration PostgreSQL.
- Avantages : officiel, fiable.
- Inconvénients : nécessite orchestration.
- Recommandation : utiliser dès bêta.

### WAL / sauvegardes managées

- Recommandation : privilégier PostgreSQL managé si budget possible ; sinon documenter cron + stockage externe + test restore.

## Tests backend

### Node test runner

- Source : https://nodejs.org/api/test.html
- Rôle : tests natifs Node.
- Avantages : pas de dépendance lourde.
- Inconvénients : écosystème moins riche que Vitest/Jest.
- Recommandation : utiliser si projet simple.

### Vitest

- Source : https://vitest.dev/
- Rôle : test runner moderne.
- Avantages : rapide, assertions, mocks.
- Inconvénients : setup.
- Recommandation : tester si build moderne.

### Supertest

- Source : https://github.com/ladjs/supertest
- Rôle : tests HTTP.
- Avantages : utile pour APIs Node.
- Inconvénients : souvent couplé patterns Express mais utilisable avec serveur HTTP.
- Recommandation : utiliser/tester pour routes.

### Testcontainers

- Source : https://node.testcontainers.org/
- Rôle : PostgreSQL réel en tests.
- Avantages : tests réalistes migrations/isolation.
- Inconvénients : Docker requis.
- Recommandation : utiliser en CI si disponible ; sinon scripts PostgreSQL local.

## Monitoring

### Sentry

- Source : https://docs.sentry.io/platforms/javascript/guides/node/
- Rôle : erreurs backend/frontend.
- Avantages : rapide à intégrer, traces.
- Inconvénients : service externe.
- Recommandation : utiliser pour bêta si budget accepté.

### OpenTelemetry

- Source : https://opentelemetry.io/docs/languages/js/
- Rôle : traces/metrics/logs standardisées.
- Avantages : standard ouvert.
- Inconvénients : plus complexe.
- Recommandation : plus tard, pas avant stabilisation.

## Feature flags

### Unleash

- Source : https://www.getunleash.io/
- Rôle : feature flags open source/commercial.
- Avantages : mature.
- Inconvénients : service à opérer.
- Recommandation : plus tard.

### Flags maison en base

- Rôle : flags simples par organisation/utilisateur.
- Avantages : suffisant en bêta.
- Inconvénients : moins de ciblage avancé.
- Recommandation : utiliser maintenant si besoin.

## Configuration d’environnement

### dotenv

- Source : https://github.com/motdotla/dotenv
- Rôle : variables d’environnement locales.
- Avantages : simple, mature.
- Inconvénients : ne remplace pas une gestion de secrets.
- Recommandation : utiliser en dev.

### envalid

- Source : https://github.com/af/envalid
- Rôle : validation env vars.
- Avantages : évite démarrage avec config invalide.
- Inconvénients : petite dépendance.
- Recommandation : utiliser/tester.

## Options nécessitant migration d’architecture

- Next.js full-stack : forte migration frontend/backend.
- NestJS : structure complète, DI, controllers ; puissant mais lourd pour l’existant.
- Fastify : migration serveur HTTP possible, plus légère qu’Express/Nest, mais reste architecture à planifier.
- Prisma : puissant mais impose workflow ORM/migrations ; intéressant si TypeScript et modèle relationnel stabilisé.

## Recommandation backend initiale

1. `pg` pour PostgreSQL.
2. `node-pg-migrate` stable ou `dbmate` pour migrations SQL.
3. Zod pour validation API/imports.
4. Sessions serveur en PostgreSQL pour bêta privée.
5. Pino pour logs.
6. Playwright/Supertest/Node test runner pour tests HTTP et isolation.
7. pg_dump + procédure restore documentée.
8. S3 compatible storage plus tard pour images/exports.
