## API Report File for "@backstage/integration"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts

import { Config } from '@backstage/config';
import { RestEndpointMethodTypes } from '@octokit/rest';

// @public (undocumented)
export class AzureIntegration implements ScmIntegration {
    constructor(integrationConfig: AzureIntegrationConfig);
    // (undocumented)
    get config(): AzureIntegrationConfig;
    // (undocumented)
    static factory: ScmIntegrationsFactory<AzureIntegration>;
    // (undocumented)
    resolveEditUrl(url: string): string;
    // (undocumented)
    resolveUrl(options: {
        url: string;
        base: string;
        lineNumber?: number;
    }): string;
    // (undocumented)
    get title(): string;
    // (undocumented)
    get type(): string;
}

// @public
export type AzureIntegrationConfig = {
    host: string;
    token?: string;
};

// @public (undocumented)
export class BitbucketIntegration implements ScmIntegration {
    constructor(integrationConfig: BitbucketIntegrationConfig);
    // (undocumented)
    get config(): BitbucketIntegrationConfig;
    // (undocumented)
    static factory: ScmIntegrationsFactory<BitbucketIntegration>;
    // (undocumented)
    resolveEditUrl(url: string): string;
    // (undocumented)
    resolveUrl(options: {
        url: string;
        base: string;
        lineNumber?: number;
    }): string;
    // (undocumented)
    get title(): string;
    // (undocumented)
    get type(): string;
}

// @public
export type BitbucketIntegrationConfig = {
    host: string;
    apiBaseUrl?: string;
    token?: string;
    username?: string;
    appPassword?: string;
};

// @public
export function defaultScmResolveUrl(options: {
    url: string;
    base: string;
    lineNumber?: number;
}): string;

// @public
export function getAzureCommitsUrl(url: string): string;

// @public
export function getAzureDownloadUrl(url: string): string;

// @public
export function getAzureFileFetchUrl(url: string): string;

// @public
export function getAzureRequestOptions(config: AzureIntegrationConfig, additionalHeaders?: Record<string, string>): RequestInit;

// @public
export function getBitbucketDefaultBranch(url: string, config: BitbucketIntegrationConfig): Promise<string>;

// @public
export function getBitbucketDownloadUrl(url: string, config: BitbucketIntegrationConfig): Promise<string>;

// @public
export function getBitbucketFileFetchUrl(url: string, config: BitbucketIntegrationConfig): string;

// @public
export function getBitbucketRequestOptions(config: BitbucketIntegrationConfig): RequestInit;

// @public
export function getGitHubFileFetchUrl(url: string, config: GitHubIntegrationConfig): string;

// @public
export function getGitHubRequestOptions(config: GitHubIntegrationConfig): RequestInit;

// @public
export function getGitLabFileFetchUrl(url: string, config: GitLabIntegrationConfig): Promise<string>;

// @public
export function getGitLabRequestOptions(config: GitLabIntegrationConfig): RequestInit;

// @public (undocumented)
export class GithubAppCredentialsMux {
    constructor(config: GitHubIntegrationConfig);
    // (undocumented)
    getAllInstallations(): Promise<RestEndpointMethodTypes['apps']['listInstallations']['response']['data']>;
    // (undocumented)
    getAppToken(owner: string, repo?: string): Promise<string | undefined>;
}

// @public (undocumented)
export class GithubCredentialsProvider {
    // (undocumented)
    static create(config: GitHubIntegrationConfig): GithubCredentialsProvider;
    getCredentials(opts: {
        url: string;
    }): Promise<GithubCredentials>;
    }

// @public (undocumented)
export type GithubCredentialType = 'app' | 'token';

// @public (undocumented)
export class GitHubIntegration implements ScmIntegration {
    constructor(integrationConfig: GitHubIntegrationConfig);
    // (undocumented)
    get config(): GitHubIntegrationConfig;
    // (undocumented)
    static factory: ScmIntegrationsFactory<GitHubIntegration>;
    // (undocumented)
    resolveEditUrl(url: string): string;
    // (undocumented)
    resolveUrl(options: {
        url: string;
        base: string;
        lineNumber?: number;
    }): string;
    // (undocumented)
    get title(): string;
    // (undocumented)
    get type(): string;
}

// @public
export type GitHubIntegrationConfig = {
    host: string;
    apiBaseUrl?: string;
    rawBaseUrl?: string;
    token?: string;
    apps?: GithubAppConfig[];
};

// @public (undocumented)
export class GitLabIntegration implements ScmIntegration {
    constructor(integrationConfig: GitLabIntegrationConfig);
    // (undocumented)
    get config(): GitLabIntegrationConfig;
    // (undocumented)
    static factory: ScmIntegrationsFactory<GitLabIntegration>;
    // (undocumented)
    resolveEditUrl(url: string): string;
    // (undocumented)
    resolveUrl(options: {
        url: string;
        base: string;
        lineNumber?: number;
    }): string;
    // (undocumented)
    get title(): string;
    // (undocumented)
    get type(): string;
}

// @public
export type GitLabIntegrationConfig = {
    host: string;
    apiBaseUrl: string;
    token?: string;
    baseUrl: string;
};

// @public
export type GoogleGcsIntegrationConfig = {
    clientEmail?: string;
    privateKey?: string;
};

// @public
export function readAzureIntegrationConfig(config: Config): AzureIntegrationConfig;

// @public
export function readAzureIntegrationConfigs(configs: Config[]): AzureIntegrationConfig[];

// @public
export function readBitbucketIntegrationConfig(config: Config): BitbucketIntegrationConfig;

// @public
export function readBitbucketIntegrationConfigs(configs: Config[]): BitbucketIntegrationConfig[];

// @public
export function readGitHubIntegrationConfig(config: Config): GitHubIntegrationConfig;

// @public
export function readGitHubIntegrationConfigs(configs: Config[]): GitHubIntegrationConfig[];

// @public
export function readGitLabIntegrationConfig(config: Config): GitLabIntegrationConfig;

// @public
export function readGitLabIntegrationConfigs(configs: Config[]): GitLabIntegrationConfig[];

// @public
export function readGoogleGcsIntegrationConfig(config: Config): GoogleGcsIntegrationConfig;

// @public
export interface ScmIntegration {
    resolveEditUrl(url: string): string;
    resolveUrl(options: {
        url: string;
        base: string;
        lineNumber?: number;
    }): string;
    title: string;
    type: string;
}

// @public
export interface ScmIntegrationRegistry extends ScmIntegrationsGroup<ScmIntegration> {
    // (undocumented)
    azure: ScmIntegrationsGroup<AzureIntegration>;
    // (undocumented)
    bitbucket: ScmIntegrationsGroup<BitbucketIntegration>;
    // (undocumented)
    github: ScmIntegrationsGroup<GitHubIntegration>;
    // (undocumented)
    gitlab: ScmIntegrationsGroup<GitLabIntegration>;
    resolveEditUrl(url: string): string;
    resolveUrl(options: {
        url: string;
        base: string;
        lineNumber?: number;
    }): string;
}

// @public (undocumented)
export class ScmIntegrations implements ScmIntegrationRegistry {
    constructor(integrationsByType: IntegrationsByType);
    // (undocumented)
    get azure(): ScmIntegrationsGroup<AzureIntegration>;
    // (undocumented)
    get bitbucket(): ScmIntegrationsGroup<BitbucketIntegration>;
    // (undocumented)
    byHost(host: string): ScmIntegration | undefined;
    // (undocumented)
    byUrl(url: string | URL): ScmIntegration | undefined;
    // (undocumented)
    static fromConfig(config: Config): ScmIntegrations;
    // (undocumented)
    get github(): ScmIntegrationsGroup<GitHubIntegration>;
    // (undocumented)
    get gitlab(): ScmIntegrationsGroup<GitLabIntegration>;
    // (undocumented)
    list(): ScmIntegration[];
    // (undocumented)
    resolveEditUrl(url: string): string;
    // (undocumented)
    resolveUrl(options: {
        url: string;
        base: string;
        lineNumber?: number;
    }): string;
}

// @public
export interface ScmIntegrationsGroup<T extends ScmIntegration> {
    byHost(host: string): T | undefined;
    byUrl(url: string | URL): T | undefined;
    list(): T[];
}


// (No @packageDocumentation comment for this package)

```
