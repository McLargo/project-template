# Rollout plan

| Target Date   | Status   | Author                                 |
| :-----------: | :------: | :------------------------------------: |
| XX/XX/XXXX    | Accepted | If applicable, add author name here    |

Status can be one of the following:

- Draft: when the Rollout plan is still in draft mode.
- Accepted: when the Rollout plan is accepted and will be implemented.
- Rejected: when the Rollout plan is rejected and will not be implemented.

This documents aims the process you may need to follow to rollout new projects
or features in production. It is a generic document, so more details may be
added to your rollout plan depending on the project (feature flags are
implemented, UAT is mandatory...). The goal is to have a list of scope items to
be checked before, during and after the rollout.

## Before rollout

- [ ] Product and business readiness: product owners and corresponding
  stakeholders have reviewed the feature and agree that it is ready to go live
  to the final user.
- [ ] UAT testing and QA: the feature has been tested in a staging environment
  and all tests have passed.
- [ ] Regression testing: all regression tests have passed, to confirm the
  feature does not break existing functionality.
- [ ] Load testing: the feature has been tested under load and stress conditions
  to ensure it can handle the expected traffic.
- [ ] Observability and monitoring: dashboards, alerts and logging have been
  implemented and tested.
- [ ] Infrastructure readiness: the infrastructure is ready to support the
  feature (kubernetes resources, database migrations, new topics, cloud
  infrastructure) are in place.
- [ ] API Keys and secrets management: all API keys and secrets are stored in a
  secure location (Vault, Secret Manager) and are not hardcoded in the codebase.
- [ ] Permissions and authentication: all permissions and authentication
  mechanisms have been reviewed and tested to ensure that only authorized users
  can access the feature.
- [ ] Confirm dependencies: all dependencies (third-party services, internal
  libraries,or APIs) have been confirmed to be available and working as
  expected. Ideally, all integration tests should pass in a staging environment.
- [ ] Define the release strategy: define the release strategy (feature flags,
  canary releases, blue-green deployments).
- [ ] Define the rollback plan in case of issues. It must be include what
  technical and product metrics will be monitored to determine if a rollback is
  needed, and the steps to rollback the feature if necessary (e.g. disable
  feature flag, rollback database migrations, etc.).
- [ ] All teams involved in the rollout are aware of the plan and their
  responsibilities during the rollout process.
- [ ] Define the communication plan: define the communication plan to notify
  stakeholders and users about the rollout, including any expected downtime or
  changes in functionality.

> NOTE: All these items can be expanded with more details depending on the
> project.

## During rollout

- [ ] Code freeze: no new code changes are allowed during the rollout process.
- [ ] Notify stakeholders: all stakeholders should be notified of the rollout and
  the expected timeline.
- [ ] Deployment: the feature is deployed to production and verified that it is
  running correctly (ping/status endpoints, smoke tests, etc.).
- [ ] Enable the feature: if the feature is behind a feature flag, enable it for
  the target audience (canary release, percentage rollout, etc.).

## After rollout

- [ ] Monitor metrics: monitor the metrics and logs to ensure that the feature is
  working as expected and that there are no issues.
- [ ] Notify stakeholders: notify stakeholders that the rollout is complete and
  provide any relevant information about the feature.
- [ ] Resolve any incidents: after triage, provide guidance and support to
  resolve any incidents that may arise after the rollout process. Provide a
  post-mortem report if necessary.
- [ ] Inform on-call teams: inform on-call teams about the rollout and any
  potential issues that may arise.
- [ ] Retrospective: schedule a retrospective meeting to review the rollout
  process and identify any areas for improvement for future rollouts.
