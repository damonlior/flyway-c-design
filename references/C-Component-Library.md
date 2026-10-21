# Flyway C Component Library Map

## Authoritative source

- Figma file: `❖ 飞来汇设计规范 - C端 V1.0`
- File key: `TKHzEYvXwFS10wSNHK7EGC`
- Library key: `lk-682f07f5ed8ef1580517f163e09c1133256cc6d7aa91d80381e4b5fd85aae6972163c5634b4b7dcd2f96207858090d3dd0753cc44c77ea3660723d390d14aba9`
- Source URL: https://www.figma.com/design/TKHzEYvXwFS10wSNHK7EGC/%E2%9D%96-%E9%A3%9E%E6%9D%A5%E6%B1%87%E8%AE%BE%E8%AE%A1%E8%A7%84%E8%8C%83---C%E7%AB%AF-V1.0?node-id=20416-22&p=f
- Verified: 2026-10-21 through the `Figma` connection.

This file overrides every B-library component name, key, availability claim, Variable, and Style in the inherited documents. The inherited documents still govern workflow, usage, states, risk, permissions, Auto Layout, responsive behavior, and delivery unless this map says otherwise.

## Source lock

1. Resolve source components, Variables and Styles from C file `TKHzEYvXwFS10wSNHK7EGC`. Write page instances only into the user-authorized destination file/frame; this source key is not an instruction to edit the component library.
2. For design-system search, pass `includeLibraryKeys: [<the full C library key above>]` and confirm `libraryName` is exactly `❖ 飞来汇设计规范 - C端 V1.0`.
3. Never import or instantiate an asset whose library is the B-end V2.0 library, even when its name matches.
4. If the C library has no suitable master, use a documented C composition or mark `Needs Extension`. Do not fall back to B.
5. Page IDs are discovery anchors, not permission to modify the component library. Refresh current properties before a write because component definitions can change.

## Foundations

Exact C keys and current values are recorded in [C-Token-Registry.json](C-Token-Registry.json). Use names only as lookup labels; import/bind by the corresponding C key. On the destination canvas, verify the resolved key and collection, not a potentially colliding local name. If a font, mode, size, or component property differs from inherited numeric guidance, use the current C asset and preserve the inherited usage intention; do not create a replacement token.

- `body` → `body (regular)`; `heading-5` → `heading-5 (regular)`.
- C FontWeight values: Regular=400, Medium=580, Bold=700. Emphasized Text Styles use the actual `Semibold` font style.
- Windows: `Microsoft YaHei UI`; Harmony: `HarmonyOS Sans SC`; Android Chinese: `Noto Sans CJK SC`. Bind the C FontFamily variable rather than inheriting approximate names.

### Library-internal dependency exception

The C `Color` collection currently contains 14 reverse-color Variables whose aliases reference 17 remote Variables in the B `_Primitives` collection (confirmed by matching the remote collection key against the B file). This is a dependency inside the Figma library, not a valid fallback mapping. These 14 Variables are blocked for automatic use until the library maintainer migrates the aliases to C-local primitives. Do not import the remote primitive keys, copy their values, or silently replace these Variables. Mark required reverse-color capability `Needs Extension` / 待迁移. Ordinary C-local semantic variables remain available.

Blocked C Token names:

- `Text icon reverse/color-text-icon-reverse-tertiary`
- `Text icon reverse/color-text-icon-reverse-secondary`
- `Text icon reverse/color-text-icon-reverse-primary`
- `Surface reverse/color-surface-reverse-active`
- `Surface reverse/color-surface-reverse-hover`
- `Surface reverse/color-surface-reverse-secondary`
- `Line reverse/color-line-reverse-border-light`
- `Line reverse/color-line-reverse-border-regular`
- `Line reverse/color-line-reverse-separator-regular`
- `Surface reverse/color-surface-reverse-tertiary`
- `Text icon reverse/color-text-icon-reverse-quaternary`
- `Line reverse/color-line-reverse-border-dark`
- `Line reverse/color-line-reverse-separator-dark-`
- `Surface reverse/color-surface-reverse-primary`

### Available C families

Use C-library Variables and Styles only. Verified families include:

- Color: `Basic/*`, `Info/*`, `Success/*`, `Warning/*`, `Danger/*`, `Link/*`, `Surface/*`, `Text icon/*`, `Line/*`, `Disable/*`.
- Spacing: `spacing-0`, `spacing-xs`, `spacing-s`, `spacing-m`, `spacing-l` and the remaining C collection values.
- Radius: `radius-0`, `radius-s`, `radius-m`, `radius-xl` and the remaining C collection values.
- Text styles: `body-*`, `heading-*`, and the C file's other published text styles.
- Effects: `shadow-s`, `shadow-m`, `shadow-l`.
- Grid and width values: use only the current C-file definitions; do not reuse a B value by name without resolving it from the C library.

## Full C component registry

[C-Component-Registry.json](C-Component-Registry.json) records the current local component identities across all 58 marked asset pages, including all Component Sets and standalone Components. The four core pages also record their actual property definitions. This registry is the lookup evidence for the mappings below; repeated names such as `Modal` and `_Body` must be disambiguated by page and key.

## Core component mapping

| Capability | C component or composition | C page anchor | Mapping note |
|---|---|---:|---|
| Button | `01_Button`; `02_Button Group` | `48:532` | Type uses `Primary-Fill` / `Primary-Fill-Reverse`. |
| Link | `Link` | `17184:61888` | Default and underline types with Default/Hover/Active/Visited. |
| Form / Input | `_04_Without Label`, `01_表单（顶对齐）`, `02_表单（左对齐）`, `03_表单（右对齐）` | `17184:65938`, `34:1769` | Input capabilities are Form variants; no separate C `Input` master was found. |
| Radio / Checkbox | `01_单复选项`, `02_单复选图标` | `17184:63619` | Use selected/disabled properties from the C set. |
| Switch | `Switch` | `10579:6422` | On/off and disabled properties. |
| Select | `分段选择`, `Cell/勾选角标`, `Cell/按钮选项`, `高优项选择`; Form variants for field shells | `216:3719` | Do not use B-only same-name keys. |
| Cascader | Form composition | `11853:12657` | C page contains Form instances rather than a standalone Cascader master. |
| Date Picker | `日历控件`, `支持快捷选择的日期区间` | `202:2642` | Includes year, month, date and range types. |
| Rating | `评分` | `314:4384` | 0–5 including 2.5. |
| Upload | `_文件类型图标`, `_文件列表`, `02_拖拽样式`, `Cell/默认样式`, `01_表单样式（默认）`, `Cell/卡片样式（指定文件）` | `420:3901` | Includes form, drag, card, file-list and document-type states. |
| Dropdown | `_dropdown menu item`, `下拉菜单` | `299:3856` | C items include regular selection, country/region, status, address and action types. |
| Modal / Sheet | `Modal`, `Sheet（移动端）`, `Cell / Header`, `Cell / Bottom`, `_Body` | `295:3908` | `Cell / Bottom` must not be used alone. |
| Table | `01_表头`, `02_单元格`, `03_操作`, `03 批量操作栏` | `17184:65939` | Current canvas name `02_单元格` shares C key `26a06ae5868e1f3ca4091bcc7dc3f3b3d9d6658c` with published alias `02_td`. Resolve by key, not name. |
| Drawer | `Drawer` | `10960:3935` | Sizes s/m/l. |
| Collapse | `Collapse` | `11461:1339` | On/off variants. |
| Card | No formal generic Card master | `295:3884` | Page is marked under construction and empty. Use a controlled composition or `Needs Extension`. |
| Dialog | `Modal` danger/regular confirmation variants | `17184:65935` | Choose according to interruption and risk. |
| Popconfirm | `Popconfirm` | `17184:65936` | Regular/danger and four arrow positions. |
| Notification | `Notification Card` | `17184:65937` | P0/P1 levels. |
| Toast | `Toast` | `17078:5849` | Regular/warning/error/success. |
| Alert | `Alert` | `322:3230` | Single/multiline and semantic types. |
| Progress | `加载进度条` | `314:4077` | Use actual progress values; existing variants show 25/50/100%. |
| Tag | `01_tag`, `02_Tag Group` | `319:3047` | C master is lowercase `tag`. |
| Tooltip | `Tooltips` | `371:5289` | Four arrow positions. |
| Badge | `徽标` | `17184:65759` | Single/multiple character and dot variants. |
| Placeholder | `Placeholder` | `19229:7702` | Avatar/image/product/file. It is not an Empty State. |
| Preview | `Image`, `Preview` | `338:4063` | Use current C variants. |
| Tab | `_标签`, `Tab` | `200:1604` | Text primary and button secondary forms. |
| Breadcrumb | `Breadcrumb` | `11758:823` | Use C instance. |
| Pagination | `_Cell/页数`, `Pagination` | `208:2560` | Default, minimal and mini. |
| Anchor | `_Cell`, `Anchor` | `17284:66475` | Selected/unselected. |
| Steps | C Steps component sets | `319:2948` | Horizontal/vertical and business states. |
| Timeline | `Timeline` and supporting sets | `9408:726` | Ascending/descending time direction. |
| Scrollbar | `_Scrollbar` | `17537:7731` | 25/50/75% lengths. |

## C-end business mapping

| Capability | C component | Page anchor |
|---|---|---:|
| Country / region and phone | `国家地区号码`, `国家地区`, `Menu items` | `17184:65947` |
| Currency and amount | `币种和金额选择` | `17184:65940` |
| Exchange-rate change | `汇率变化` | `17184:65948` |
| Password / security verification | `_Password Input`, `_Body`, `Security Verification` | `17184:65943` |
| Verification code | `Verification Code Verification` | `17184:65949` |
| Usage guide | `Guide` | `17184:65945` |

The following B-end mappings were not found as C-library capabilities and must not be reused automatically: recipient/account selectors, bank-card components, authorization components, B-end operations popups, and B-end-only business packages.

## Empty and result mapping

- Empty page `20416:22` shows 38 approved instances: 34 general/business scenes and 4 fund status scenes. No C-local complete Empty State container master was verified. The existing illustration instances do not prove their masters originate in C. Check each main component and any nested instances before reuse; if its origin is external, mark `Needs Extension` instead of cloning an external-library instance.
- `操作结果` page `20416:168`, `页尾` page `19215:1977`, and `协议` page `19215:1978` are currently empty. Do not claim formal components exist.
- Email page `19215:1979` contains `_Details`, `_Contact`, `Footer`, and a FlyLink Logo instance; treat it as an email-specific composition.

## Validation before delivery

For reused instances, validate the main Component/Component Set key and any nested Component instances. For bound variables, validate both the semantic C key and alias dependency chain. Imported C assets may themselves contain external dependencies: report or block them rather than treating the C top-level name as proof that every dependency is C-local.


Report the C file key, reused C component names, any compositions, and every missing asset. A result is not C-library compliant if any component or token resolved from the B library or if a blank/under-construction page was presented as a formal component.
