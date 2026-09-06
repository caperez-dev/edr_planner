# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Stack

static HTML with Tailwind CSS and Lucide Icons loaded from CDNs

## Users

Tata Consultancy Services employees who prepare, coordinate, review, or execute application implementation and maintenance-of-procedure plans.

## Product Purpose

EDR Planner turns application MOP JSON data into a searchable, filterable execution plan. Success means employees can inspect the plan and edit task details directly in the planner when the imported data needs clarification or operational updates.

## Operating Context

The planner is used in a web browser with application MOP JSON files selected locally. Users work across application lists and task tables, and may need to review ownership, timing, comments, and issues while preparing an execution plan.

## Capabilities and Constraints

- Import one or more local MOP JSON files.
- View applications and their tasks in a table.
- Search tasks and filter applications.
- Expand or collapse task groups and clear the current plan.
- Edit task descriptions, details, types, owners, and comments in the browser.
- Toggle table columns and restore the default column state.
- The current implementation is a single HTML file with no backend or server-side persistence.

## Evidence on Hand

- Main application: `edrplanner.html`
- Sample MOP data: `data/app1_edr_mop.json` and `data/app2_edr_mop.json`
- No testimonials, customer evidence, or other proof assets are present.

## Product Principles

- Keep operational plans easy to inspect and update.
- Preserve the structure and meaning of imported MOP data.
- Make ownership, timing, comments, and issues easy to review.
- Favor local, direct workflows that do not require backend setup.
