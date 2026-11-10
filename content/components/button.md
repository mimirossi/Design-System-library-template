---
title: Button
group: Actions
order: 10
type: component
status: Draft
description: Triggers an action, such as submitting a form or opening a dialog.
figma:
---

## Overview

> [!TODO]
> **What it is and when to use it.** Two or three sentences, then when to pick this component and when to pick another one.

![Button overview](assets/images/button/overview.png)

## Anatomy

![Button anatomy](assets/images/button/anatomy.png)

> [!TODO]
> **Numbered parts.** List each part marked in the anatomy image: 1. Container · 2. Label · 3. Icon…

## Variants

> [!TODO]
> **Variants and sizes.** One image or live preview per variant, with a line on when to use it.

![Button variants](assets/images/button/variants.png)

## States

> [!TODO]
> **States.** Default, hover, focus, active, disabled, loading, error — whichever apply.

![Button states](assets/images/button/states.png)

## Usage

> [!TODO]
> **Do and don't.** Rewrite the two boxes below. An image can go inside each box.

> [!DO]
> Replace with a correct usage example.

> [!DONT]
> Replace with a usage to avoid.

## Code

> [!TODO]
> **Snippets.** Replace the example below with the real code. Keep the `preview` flag to show the HTML rendered.

```import type { ButtonHTMLAttributes } from "react";

export type ButtonVariant = "Default" | "Secondary" | "Outline" | "Ghost" | "Destructive" | "Link";

export type ButtonState = "Default" | "Hover" | "Focus" | "Active" | "Disabled";

type ButtonProps = Omit<ButtonHTMLAttributes<HTMLButtonElement>, "disabled"> & {
  label?: string;
  state?: ButtonState;
  variant?: ButtonVariant;
};

const variantClasses: Record<ButtonVariant, string> = {
  Default:
    "border-transparent bg-[#a0187c] text-[#fffdf7] hover:bg-[rgba(160,24,124,0.8)] active:bg-[#a0187c]",
  Secondary:
    "border-transparent bg-[#fae2f3] text-[#a0187c] hover:bg-[#edd7e7] active:bg-[#fae2f3]",
  Outline: "border-[#767676] bg-[#fffdf7] text-[#1c1c1c] hover:bg-[#f5f1e7] active:bg-[#fffdf7]",
  Ghost:
    "border-transparent bg-transparent text-[#1c1c1c] hover:bg-[#f5f1e7] active:bg-transparent",
  Destructive:
    "border-transparent bg-[rgba(231,0,11,0.1)] text-[#e7000b] hover:bg-[rgba(231,0,11,0.2)] active:bg-[rgba(231,0,11,0.1)]",
  Link: "border-transparent bg-transparent px-0 text-[#a0187c] underline decoration-solid underline-offset-auto",
};

const stateClasses: Record<ButtonState, string> = {
  Default: "",
  Hover: "",
  Focus: "button-focus-ring",
  Active: "",
  Disabled: "opacity-50",
};

const previewOverrides: Record<ButtonVariant, Partial<Record<ButtonState, string>>> = {
  Default: {
    Hover: "bg-[rgba(160,24,124,0.8)]",
    Active: "bg-[#a0187c]",
  },
  Secondary: {
    Hover: "bg-[#edd7e7]",
    Active: "bg-[#fae2f3]",
  },
  Outline: {
    Hover: "bg-[#f5f1e7]",
    Active: "bg-[#fffdf7]",
  },
  Ghost: {
    Hover: "bg-[#f5f1e7]",
    Active: "bg-transparent",
  },
  Destructive: {
    Hover: "bg-[rgba(231,0,11,0.2)]",
    Active: "bg-[rgba(231,0,11,0.1)]",
  },
  Link: {},
};

export default function Button({
  className = "",
  label = "Button",
  state = "Default",
  variant = "Default",
  type = "button",
  ...props
}: ButtonProps) {
  const disabled = state === "Disabled";
  const isLink = variant === "Link";

  return (
    <button
      {...props}
      type={type}
      disabled={disabled}
      data-state={state}
      data-variant={variant}
      className={[
        "button-base",
        isLink ? "button-link" : "px-4",
        variantClasses[variant],
        stateClasses[state],
        previewOverrides[variant][state] ?? "",
        className,
      ].join(" ")}
    >
      {label}
    </button>
  );
}

```

## Props

> [!TODO]
> **API table.** One row per prop, attribute or class modifier.

| Prop | Type | Default | Description |
| --- | --- | --- | --- |
| `variant` | `primary`, `secondary` | `primary` | Visual style |

## Design tokens

> [!TODO]
> **Tokens used.** List the tokens this component reads, or point a `tokens` block at the Figma export.

## Accessibility

> [!TODO]
> **Requirements.** Keyboard interaction, focus order, ARIA attributes, minimum contrast and target size.

## Figma

> [!TODO]
> **Figma link.** Paste the link to the component on a line of its own: it becomes an embedded frame. Add it to `figma:` at the top of this file too.

## Changelog

> [!TODO]
> **History.** `YYYY-MM-DD` — what changed.
