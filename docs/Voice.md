# Voice and wording

The wording rules and glossaries of each language in this pack. Loading and the file layout are in the
[README](../README.md).

A mark that is not part of the word (`:`, `*`, ` #`) stays outside the message when the plain word is the same message. A question keeps its `?` in the message, since Spanish needs `¿…?`. The screen or service appends the mark, as `localize("Status") + ": "`. A sentence used in more than one place uses one `${}` template; call sites share that placeholder text, with a local when the expression would otherwise differ. Do not fold a mark into the key when the marked form is a different word (`Check` / `Check #`, `Account` / `Account #`).

## Spanish (es)

Locale `es` is neutral international Spanish: Latin American words that Spain also understands.

| English | es |
| --- | --- |
| computer | computadora |
| file | archivo |
| mobile phone | celular |
| email | correo electrónico |
| password | contraseña |
| settings | configuración |
| save | guardar |
| default | predeterminado |

Actions use the infinitive (Guardar, Cancelar). The `es` files do not use ordenador, fichero, móvil, vosotros, or voseo.

`EsRegional.xml` is a short overlay, not a second catalog:

- `es_ES`: fichero, móvil, and ajustes where the English is Settings. No label in this pass is Computer, so there is no ordenador row.
- `es_MX` has no rows of its own. archivo, celular, and configuración come from `es`.

These nine originals stay in `framework/data/CommonL10nData.xml` and are not repeated here: Add, Create, Delete, Description, Find, Name, Status, Type, Update.

A Spanish row is stored only when the text differs from the fallback: the original English, or the `default` template when one exists. A missing row returns that fallback. `es_MX` uses the `es` row.

Placeholders `${...}` and `{0}` `{1}` `{2}` `{3}` are copied unchanged. A `##` suffix stays on the key when its Spanish differs from the words before `##`. Strings longer than 255 characters cannot be keys.

## Simplified Chinese (zh)

Locale `zh` is Simplified Chinese, mainland UI wording, the same script as the `zh` rows in `CommonL10nData.xml`. There is no `zh_CN`, `zh_TW`, or `zh_HK` file. Traditional Chinese is a later catalog: a missing `zh_TW` row would fall back to Simplified `zh` before English.

The nine seed originals stay in `framework/data/CommonL10nData.xml` and are not repeated here.

A colon the screen appends to a label is half-width (`状态: `); a colon inside a translated message is full-width `：`.

Labels are short bare verbs (保存, 取消). Financial and GL account is 账户 (户, not 帐户). A login account is 账号. Shipment is 发货单. Party is 参与方. The token PO stays PO. Moqui, MR Moqui, Marble, and Mantle stay as written. `N/A` inside a template literal is 无.

| English | zh |
| --- | --- |
| Save | 保存 |
| Cancel | 取消 |
| Close | 关闭 |
| Submit | 提交 |
| Confirm | 确认 |
| Search | 搜索 |
| Edit | 编辑 |
| View | 查看 |
| Print | 打印 |
| Export | 导出 |
| Import | 导入 |
| New | 新建 |
| Copy | 复制 |
| Remove | 移除 |
| Settings | 设置 |
| File | 文件 |
| Email | 电子邮件 |
| Password | 密码 |
| User | 用户 |
| Username | 用户名 |
| Invoice | 发票 |
| Bill | 账单 |
| Order | 订单 |
| Purchase order | 采购订单 |
| Shipment | 发货单 |
| Party | 参与方 |
| Customer | 客户 |
| Supplier, Vendor | 供应商 |
| Employee | 员工 |
| Account (financial) | 账户 |
| Account (login) | 账号 |
| Accounting | 会计 |
| GL | 总账 |
| Payment | 付款 |
| Product | 产品 |
| Inventory | 库存 |
| Asset | 资产 |
| Facility | 设施 |
| Warehouse | 仓库 |
| Quantity | 数量 |
| Amount | 金额 |
| Price (unit) | 单价 |
| Active | 有效 |
| Cancelled | 已取消 |
| Completed | 已完成 |
| Approved | 已批准 |
| Pending | 待处理 |
| Draft | 草稿 |
| Mobile | 手机 |

Do not use 軟體, 資訊, 預設, 檔案, 設定, 網路, 程式 (程序 is the word; 方程式 may stay), 視窗, 螢幕, 滑鼠, 資料, or Cantonese 嘅 喺 唔 佢 咗 啲. Use 软件, 信息, 默认, 文件, 设置, 网络, 程序, 窗口, 屏幕, 鼠标, 数据.

A `zh` row is stored only when the text differs from the English original. The omitted originals are listed in `data/zh/unchanged-*.txt`, which the loader ignores. This pack follows the Spanish key set. A name that is spelled the same in English and Spanish, such as China or a province written in English, has no row in either pack, so a `zh` user still sees that English name. Placeholders `${...}` and `{0}` `{1}` `{2}` `{3}` are copied unchanged, including a `{n,choice,...}` pattern. Natural-language words inside a `${}` string literal are translated (`'No Lot #'`, `'N/A'`). A `##` inside a number pattern such as `#,##0.00` or `###-###` stays. The localized value is at most 255 characters.

## Boss apps

Commons, Comms, and Projects add these words. Use them for that sense wherever the English says so. Words already in the pack stay as stored: Party is Participante / 参与方, Work item is Elemento de trabajo / 工作项, Timesheet is Hoja de horas / 工时表, Milestone is Hito / 里程碑, Repository is Repositorio / 代码库, Task is Tarea / 任务, Request is Solicitud / 请求, Note is Nota / 备注, Notes is Notas / 备注, Contact is Contacto / 联系人, Chat is Conversación / 聊天, Comms is Comunicaciones / 通信, Inbox is Bandeja de entrada / 收件箱, Billable is Facturable / 可计费, Commit (a git commit) is Confirmación / 提交记录, Branch is Rama / 分支, and the verb Merge is Fusionar / 合并. Submit stays 提交. Wiki Space stays Espacio Wiki.

| English | es | zh |
| --- | --- | --- |
| Sprint | Iteración | 迭代 |
| Backlog | Pendientes | 待办 |
| Merge request | Solicitud de fusión | 合并请求 |
| Roadmap | Hoja de ruta | 路线图 |
| Allocation | Asignación | 分配 |
| Drive (a file drive) | Unidad | 网盘 |
| Commons (the app) | Área común | 共享 |
| Wiki page | Página wiki | 维基页面 |
| Epic | Épica | 史诗 |
| Unbilled | Sin facturar | 未开票 |

A shell command (`git clone`, `git fetch`, `git checkout`, `git push`) stays byte for byte. Moqui, MR Moqui, Marble, Mantle, and IronStone stay as written. CalDAV, CardDAV, WebDAV, DAVx⁵, and PO stay as written.

Products, Accounting, Warehouse, Manufacturing, Purchasing, and Customer Service add these senses. Words already stored stay as stored: Warehouse is Almacén / 仓库, Facility is Instalación / 设施, Bin is Cas / 货位, Pick is Surtir / 拣货, On hand is En existencia / 现有, Replenishment is Reposición / 补充, Standard cost is Costo estándar / 标准成本, Raw material is Materia prima / 原材料, Finished good is Bien terminado / 产成品, GL account is Cuenta contable / 总账账户, and Routing is Ruta / 工艺路线.

| English | es | zh |
| --- | --- | --- |
| Bill (supplier bill) | Factura recibida | 账单 |
| Post to the ledger | Contabilizar | 过账 |
| Bank or customer statement | Estado de cuenta | 对账单 |
| Financial statement | Estado financiero | 财务报表 |
| Journal entry | Asiento | 日记账分录 |
| Cost center | Centro de costo | 成本中心 |
| Exchange rate | Tipo de cambio | 汇率 |
| Cheque | Cheque | 支票 |
| Release a hold or a blanket order | Liberar | 发放 |
| Goods receipt | Recepción | 收货 |
| Cycle count | Conteo cíclico | 循环盘点 |
| Work order | Orden de trabajo | 工单 |
| Work center | Centro de trabajo | 工作中心 |
| Bill of materials | Lista de materiales | 物料清单 |
| Shop floor | Taller | 车间 |
| Scrap | Merma | 报废 |
| Variance | Variación | 差异 |
| Put away | Ubicar | 上架 |
| Work in process | Trabajo en proceso | 在制品 |
| Subcontract | Subcontrato | 外协 |
| Inspection | Inspección | 检验 |
| Customer-service case | Caso | 案例 |
| Landed cost | Costo en destino | 到岸成本 |
| Safety stock | Stock de seguridad | 安全库存 |
| Lead time | Plazo de entrega | 提前期 |
| Backorder | Pedido pendiente | 缺货订单 |

The single stored words Post (Publicar / 发布), Statement (Sentencia / 语句), and Release (Lanzamiento / 版本) keep those older senses. A longer sentence in these apps uses the table. Payment application is aplicación / 核销. A financial account is Cuenta / 账户. PO, RFQ, ASN, BOM, WIP, MRP, OEE, SKU, RMA, UOM, GL, ATP, and NACHA stay as written when the English is the token. BOM spelled out is Lista de materiales / 物料清单.

## Later BOSS apps and PASS

The neutral catalog `File` row is Archivo / 文件. Fichero is only the `es_ES` overlay in `EsRegional.xml`. Dashboard is Panel de control / 仪表板, never Tablero. Board is Tablero / 看板. Pipeline is Canal / 管道, not 流水线. Do not add a second row for `of` (de /) or `in` (en / 属于). Constitution is Constitución / 宪章. The accounting workbench subtitle Receipts, the Incoming, Outgoing, and Transfer chips, and Check as an output stay English. Catalog Check is the verb Comprobar / 检查. Inventory receipt is Recepción / 收货. Payment receipt is Recibo / 收据. A quote-response acknowledgement is acuse / 回执.

Where two batches named the same original, the row already stored wins.

| English | es | zh | sense |
| --- | --- | --- | --- |
| Lead | prospecto | 线索 | a sales lead |
| Opportunity | oportunidad | 商机 | |
| Deal | negocio | 交易 | a lead or an opportunity |
| Sales account | cuenta | 客户账户 | the customer record, not a login or a GL account |
| Quota | cuota | 指标 | |
| Attainment | cumplimiento | 达成 | result against the quota |
| Won / Lost | ganado / perdido | 已赢 / 丢单 | a deal outcome; Lost is not missing stock |
| Qualify | calificar | 认定 | turn a lead into an opportunity |
| Hard bounce | Rebote permanente | 硬退信 | the stored row; a permanent mail failure |
| Waitlist | Lista de espera | 等候名单 | the stored row |
| Attendee | Asistente | 出席者 | the stored row |
| Ticket | Entrada | 门票 | an event ticket |
| Checkout | Finalizar compra | 结账 | the stored shop key |
| Product review | reseña | 评价 | a buyer's review; stored Reviews stays Revisiones / 审阅 |
| Delivery (stored) | Entrega | 投递 | the tools row; shop sentences use 配送 on a longer key |
| Shipping cost | Gastos de envío | 运费 | the cart charge; stored Shipping stays Envío / 发货 |
| Renewal state | Estado | 状态 | a subscription column; stored State stays Estado / 州 |
| Amount due now | A pagar ahora | 现在应付 | checkout money; stored Due now stays Vence ahora / 现在到期 |
| Leave (time off) | permiso | 休假 | not Salir / 离开 |
| Payslip | recibo de nómina | 工资单 | |
| Gross / net pay | bruto / neto | 应发 / 实发 | |
| Person who reports | subordinado | 下属 | a reporting line; a document report stays informe / 报表 |
| Work order (maintenance) | Orden de trabajo | 工单 | |
| Outage | Parada | 停运 | not the catalog Downtime row |
| Issue (to a work order) | Entregar | 发料 | stock issued to maintenance; catalog Issue stays Problema / 问题 |
| App gate | Accesos a las aplicaciones | 应用访问权限 | |
| Forum post (noun) | publicación | 帖子 | the verb Post stays Publicar / 发布 |
| Moderation report | denuncia | 举报 | not a document informe / 报表 |
| Handle | alias | 账号名 | the public forum name |
| Bookmark | marcador | 书签 | a saved post |
| Write in | Escribir en | 编写方式 | the stored row |
| Rich text | Texto enriquecido | 富文本 | the stored row |
| Fork | bifurcación | 派生 | a git fork |
| Merge request | Solicitud de fusión | 合并请求 | |
| Operator (person) | operador | 操作者 | Smithy; a forum mail operator is 操作员; catalog Operator stays 运算符 |
| Event registration | registro | 报名 | not the account-registration row 注册 |

Shop delivery sentences use Forma de entrega / 配送方式, Costo de entrega / 配送费, and Envíos de la orden / 订单发货. Do not add a second Delivery or Shipments row. A shop purchase in a new sentence is compra / 购买, not the procurement row 采购. A card ending is terminada en / 尾号. A subscription term is plazo / 期限. A rating star is estrella / 星. PASS theme phrases live in `theme/starter/locales/<locale>.json`, not in LocalizedMessage. `reviews.ofFive` is `de 5` / `（满分 5）`. Reaction keys and forum option keys stay English. Git commands stay byte for byte.
