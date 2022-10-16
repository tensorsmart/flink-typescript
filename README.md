# flink-typescript

A typescript binding auto-generated from [Apache Flink JobManager REST API](https://nightlies.apache.org/flink/flink-docs-release-1.15/docs/ops/rest_api/).

[![npm version](https://img.shields.io/npm/v/@tensorsmart/flink-typescript.svg)](https://www.npmjs.com/package/@tensorsmart/flink-typescript)
[![GitHub issues](https://img.shields.io/github/issues/tensorsmart/flink-typescript)](https://github.com/tensorsmart/flink-typescript/issues)
[![GitHub stars](https://img.shields.io/github/stars/tensorsmart/flink-typescript)](https://github.com/tensorsmart/flink-typescript/stargazers)
[![GitHub license](https://img.shields.io/github/license/tensorsmart/flink-typescript)](https://github.com/tensorsmart/flink-typescript/blob/main/LICENSE)

## Build

```shell
npm run generate
npm run compile
```

## Install

Using npm:

```shell
npm install @tensorsmart/flink-typescript
```

Using yarn:

```shell
yarn add @tensorsmart/flink-typescript
```

Using pnpm:

```shell
pnpm add @tensorsmart/flink-typescript
```

## Example

Using a model:

```typescript
import { JobStatus } from "@tensorsmart/flink-typescript";

console.log(JobStatus.RUNNING)
```

Calling a method:

```typescript
import { JobDetails, MultipleJobsDetails, DefaultService, OpenAPI } from "@tensorsmart/flink-typescript";

OpenAPI.BASE = "http://localhost:8081/v1";
DefaultService.getJobsOverview().then((response: MultipleJobsDetails) => {
    return response.jobs!.map((job: JobDetails) => new Job(this, job.jobId!, job.jobName!, job.status!));
}).catch((error: any) => {
    console.error(error);
});
```

Refer to [Flink JobManager REST API](https://nightlies.apache.org/flink/flink-docs-release-1.15/docs/ops/rest_api/) for all models and methods.

Refer to [ferdikoomen/openapi-typescript-codegen](https://github.com/ferdikoomen/openapi-typescript-codegen/blob/master/docs/openapi-object.md) for more `OpenAPI` settings.

## Projects that use this package

- [Flink JobManager client for Visual Studio Code](https://github.com/tigerinus/vscode-flink/)

## Thanks to

- [Chesnay Schepler](https://github.com/zentol) for fixing issues in Flink OpenAPI
- [Ferdi Koomen](https://github.com/ferdikoomen) for the great [OpenAPI Typescript code generator](https://github.com/ferdikoomen/openapi-typescript-codegen)

Everyone should follow them and star their projects.

