---
title: Agentic Development and Processed Food
author: David Ko
pubDatetime: 2026-02-14T11:14:00.889Z
slug: ai-ultra-process-food
featured: false
draft: false
tags:
  - Productivity
  - Entrepreneurship
  - AI
description: Filled by not full.
---

## Table of Contents

## Sense of Emptiness

Have you ever felt stuffed but not satisfied after a meal made of processed food like instant ramen or McDonald's? That's how I felt after creating a QR scanner app. I see an app in front of me, but I achieved nothing and learnt nothing, just a feeling of emptiness.

## Processed Food

We associate food that was preprocessed, and often off-the-shelf items. They are created for convenience, low cost, and a long shelf life; everything feels good, but not at the expense of your well-being. It is a quick way to create a meal in a matter of minutes.

It is so convenient that a generation almost lost the ability to cook food from scratch. Even worse, we don't exactly know what goes on in there, and many people don't care. They are energy-dense but lack essential nutrients; yet, they are cheaper to acquire and faster to consume. Without careful consumption, they can be harmful.

A few days ago, I gave agentic + vibe coding a try to create a QR code scanner and reader; oh boy, I see the result, but the feeling of emptiness rushes towards my face. Agentic coding felt like processed food. You will find the design almost the same, like a template, because the components were "off-the-shelf" from other repositories.

## AGENTS.md & SKILL.md

I wanted to give AGENTS.md and SKILL.md a try. First, I heard that it uses fewer tokens than MCP. Second, I want to learn and experience creating a React Native/Expo app with Codex. The result was that I learnt about using `npx skills add ...`, why it is needed, and why we need them.

Turns out `skills` sits inside `.agents/` directory with an array of skills, which are the references and guidelines for AI agents for specific tasks. Unlike MCP, `SKILL.md` is a guideline on what to do, rather than "shopping" for different tools and functions, hence reducing the token use.

`AGENTS.md`, where it gives the agent general guidance, much like giving an intern a handbook. In the markdown, we can specify CLI commands, coding and development styles, including Testing Driven Development (TDD).

I understand why `SKILL.md` and `AGENTS.md` have become popular. The developer has a mini development team within `./agents`, and it is convenient and arguably efficient.

Take `expo/skills` as an example; it provides detailed guidance on the best practices.

```sh
.agents
└── skills
    ├── building-native-ui
    │   ├── SKILL.md
    │   └── references
    │       ├── animations.md
    │       ├── controls.md
    │       ├── form-sheet.md
    │       ├── gradients.md
    │       ├── icons.md
    │       ├── media.md
    │       ├── route-structure.md
    │       ├── search.md
    │       ├── storage.md
    │       ├── tabs.md
    │       ├── toolbar-and-headers.md
    │       ├── visual-effects.md
    │       ├── webgpu-three.md
    │       └── zoom-transitions.md
    ...
```

````md
...
Create a shared group route so both tabs can push common screens:

```tsx
// app/(index,search)/_layout.tsx
import { Stack } from "expo-router/stack";
import { PlatformColor } from "react-native";

export default function Layout({ segment }) {
  const screen = segment.match(/\((.*)\)/)?.[1]!;
  const titles: Record<string, string> = { index: "Items", search: "Search" };

  return (
    <Stack
      screenOptions={{
        headerTransparent: true,
        headerShadowVisible: false,
        headerLargeTitleShadowVisible: false,
        headerLargeStyle: { backgroundColor: "transparent" },
        headerTitleStyle: { color: PlatformColor("label") },
        headerLargeTitle: true,
        headerBlurEffect: "none",
        headerBackButtonDisplayMode: "minimal",
      }}
    >
      <Stack.Screen name={screen} options={{ title: titles[screen] }} />
      <Stack.Screen name="i/[id]" options={{ headerLargeTitle: false }} />
    </Stack>
  );
}
```
````

By using `README.md` as a project design guideline, it is very helpful for both agents and me in checking where the project is heading; the agent usually won't deviate(too much). Pairing with TDDs, you will have a pretty solid prototype in no time, in my case, less than 30 minutes.

## Good for experienced devs but harmful to juniors

I'll be honest, for the speed to market, the agent is rather good and fast. Like processed food, it is not without long-term consequences. 1. You need to allocate most of the time to reviewing the code. 2. A project design became crucial; if the project hasn't been well thought through, you would be wasting tokens on reiterating. 3. Your programming skills and critical thinking might take a toll.

While the AI agent is generating the code for the app, I feel completely lost. When I looked at the code, if I did not know iOS and React, I would struggle to maintain the project in the long run. By typing out the code, I believe over time my brain will retain a map of the project. Just by reading the documentation, I can pick it up almost instantly. When we over-reli on AI agents, we are reducing the capabilities of our brains.

## End

At this stage of AI agentic development, we are looking at really minimum viable products (MVPs) to be even faster to market, but much like MVPs, we should expect those to be rewritten with more serious development.

But will I use agents for work? Yes, absolutely. It is a trend, it is useful, and over time, it will be more powerful. But I still strongly believe it is a smart "rubber duck"; it will be sad for me to give up the experience of struggling through a challenge and solving the problem with code that aligns with my thoughts.

Much like coding, preparing the ingredients and cooking is a process that nurtures us physically and mentally. It keeps our body and mind sharp, and I am not willing to give this up; it is more than a feeling, but survival skills.
