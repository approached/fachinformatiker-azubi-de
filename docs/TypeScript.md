---
title: TypeScript
description: Die Erweiterung für Javascrpt
published: true
date: 2022-03-21T21:20:09.849Z
tags: 
editor: markdown
dateCreated: 2022-02-21T21:23:07.840Z
---

# TypeScript

TypeScript ist eine Programmiersprache von Microsoft. Es beinhaltet die Typisierung von Javascript, dass dafür sorgt das man weniger **Fehler** im Quellcode hat. Typisierung ist abwärtskompatible und muss zu *Javascript* compiliert werden.

## Quickstart

Projekt erstellen:
```shell
yarn init
yarn add --dev typescript @types/node nodemon ts-node
```

Konfig anlegen via Befehl oder [Vorlagen](https://github.com/tsconfig/bases#node-16-tsconfigjson)
```shell
npx tsc --init
```

Build befehle anlegen in `package.json`:
```json
{
  ...
  "scripts": {
    "build": "tsc -p tsconfig.json",
    "dev": "nodemon index.ts",
    "start": "node build/index.js"
  }
  ...
}  
```

## Tutorial

Typen:
```typescript
let text: string = 'Hello World';

type MemberStatus = 'accept' | 'disable';

interface Todo {
    description: string; // text
    duration: number; // integer
    master_personId: number | string; // or
    status: 'open' | 'done' | 'closed'; // unions
    master_personStatus: MemberStatus; // unions
    persons: string | string[]; // string or array with string
    asignee?: string; // optional (text)
}

const todo: Todo = {
    description: 'Lorem Ipsum',
    duration: 20,
    master_personId: 1,
    status: 'open',
    master_personStatus: 'accept',
    persons: ['foo', 'bar']
};

const add = (one: number, two: number): number => {
    return one + two
}

const loggingText = (str: unknown): void => {
    if(typeof str === 'string'){
        console.log(str);
    }
}

const log = (data: any): void => {
    console.log(data);
}

const debug = (data: any): never => {
    throw new Error(data);
}
```

## Notizen

* [Video - Typescript lernen](https://www.youtube.com/watch?v=_CaGUZNEobk)