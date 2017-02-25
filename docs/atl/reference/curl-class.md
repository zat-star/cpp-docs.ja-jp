---
title: "CUrl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CUrl"
  - "CUrl"
  - "ATL::CUrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CUrl クラス"
ms.assetid: b3894d34-47b9-4961-9719-4197153793da
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CUrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは URL を表します。  URL の各要素をそれぞれ独立に操作して、既存の URL 文字列を解析したり、文字列を新規に組み立てたりできます。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class CUrl  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CUrl::CUrl](../Topic/CUrl::CUrl.md)|コンストラクターです。|  
|[CUrl::~CUrl](../Topic/CUrl::~CUrl.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CUrl::Canonicalize](../Topic/CUrl::Canonicalize.md)|正規形式に URL 文字列を変換するには、このメソッドを呼び出します。|  
|[CUrl::Clear](../Topic/CUrl::Clear.md)|URL\]フィールドのすべてをオフにするには、このメソッドを呼び出します。|  
|[CUrl::CrackUrl](../Topic/CUrl::CrackUrl.md)|URL をデコードおよび分析するには、このメソッドを呼び出します。|  
|[CUrl::CreateUrl](../Topic/CUrl::CreateUrl.md)|URL を作成するには、このメソッドを呼び出します。|  
|[CUrl::GetExtraInfo](../Topic/CUrl::GetExtraInfo.md)|余分な情報を得るにこのメソッドを呼び出します \(など\) か。URL からテキストや \#text\)。|  
|[CUrl::GetExtraInfoLength](../Topic/CUrl::GetExtraInfoLength.md)|補足情報の長さを取得するときにこのメソッドを呼び出します \(など\) か。URL から取得する*テキスト* または \#text\)。|  
|[CUrl::GetHostName](../Topic/CUrl::GetHostName.md)|URL からホスト名を取得するときにこのメソッドを呼び出します。|  
|[CUrl::GetHostNameLength](../Topic/CUrl::GetHostNameLength.md)|ホスト名の長さを取得するときにこのメソッドを呼び出します。|  
|[CUrl::GetPassword](../Topic/CUrl::GetPassword.md)|URL からパスワードを取得するときにこのメソッドを呼び出します。|  
|[CUrl::GetPasswordLength](../Topic/CUrl::GetPasswordLength.md)|パスワードの長さを取得するときにこのメソッドを呼び出します。|  
|[CUrl::GetPortNumber](../Topic/CUrl::GetPortNumber.md)|ATL\_URL\_PORT の点でポート番号を取得するときにこのメソッドを呼び出します。|  
|[CUrl::GetScheme](../Topic/CUrl::GetScheme.md)|URL の設定を取得するときにこのメソッドを呼び出します。|  
|[CUrl::GetSchemeName](../Topic/CUrl::GetSchemeName.md)|URL の設定の名前を取得するときにこのメソッドを呼び出します。|  
|[CUrl::GetSchemeNameLength](../Topic/CUrl::GetSchemeNameLength.md)|URL の設定の名前の長さを取得するときにこのメソッドを呼び出します。|  
|[CUrl::GetUrlLength](../Topic/CUrl::GetUrlLength.md)|URL の長さを取得するときにこのメソッドを呼び出します。|  
|[CUrl::GetUrlPath](../Topic/CUrl::GetUrlPath.md)|URL のパスを取得するときにこのメソッドを呼び出します。|  
|[CUrl::GetUrlPathLength](../Topic/CUrl::GetUrlPathLength.md)|URL のパスを取得するときにこのメソッドを呼び出します。|  
|[CUrl::GetUserName](../Topic/CUrl::GetUserName.md)|URL からユーザー名を取得するときにこのメソッドを呼び出します。|  
|[CUrl::GetUserNameLength](../Topic/CUrl::GetUserNameLength.md)|ユーザー名の長さを取得するときにこのメソッドを呼び出します。|  
|[CUrl::SetExtraInfo](../Topic/CUrl::SetExtraInfo.md)|追加情報を設定するには、このメソッドを呼び出します \(など\) か。URL の*テキスト* または \#text\)。|  
|[CUrl::SetHostName](../Topic/CUrl::SetHostName.md)|ホスト名を設定するには、このメソッドを呼び出します。|  
|[CUrl::SetPassword](../Topic/CUrl::SetPassword.md)|パスワードを設定するには、このメソッドを呼び出します。|  
|[CUrl::SetPortNumber](../Topic/CUrl::SetPortNumber.md)|ATL\_URL\_PORT の点でポート番号を設定するには、このメソッドを呼び出します。|  
|[CUrl::SetScheme](../Topic/CUrl::SetScheme.md)|URL の設定を設定するには、このメソッドを呼び出します。|  
|[CUrl::SetSchemeName](../Topic/CUrl::SetSchemeName.md)|URL の設定の名前を設定するには、このメソッドを呼び出します。|  
|[CUrl::SetUrlPath](../Topic/CUrl::SetUrlPath.md)|URL のパスを設定するには、このメソッドを呼び出します。|  
|[CUrl::SetUserName](../Topic/CUrl::SetUserName.md)|ユーザー名を設定するには、このメソッドを呼び出します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CUrl::operator \=](../Topic/CUrl::operator%20=.md)|`CUrl` の現在のオブジェクトへの `CUrl` の指定したオブジェクトを割り当てます。|  
  
## 解説  
 `CUrl` はパスまたはポート番号のような URL のフィールドを処理することができます。  `CUrl` は、次の形式の URL を理解します:  
  
 Scheme: \/\/:UserNamePassword@HostName:PortNumber\/UrlPathExtraInfo  
  
 一部のフィールドはオプションです。\) たとえば、この URL を検討する:  
  
 http:\/\/someone:secret@www.microsoft.com:80\/visualc\/stuff.htm\#contents  
  
 [CUrl::CrackUrl](../Topic/CUrl::CrackUrl.md) は次のように解析します:  
  
-   設定: 「http」や [ATL\_URL\_SCHEME\_HTTP](../Topic/ATL_URL_SCHEME.md)  
  
-   ユーザー名: 「」、  
  
-   パスワード: 「」秘密  
  
-   ホスト名: 「www.microsoft.com」  
  
-   PortNumber: 80  
  
-   UrlPath: 「」visualc\/stuff.htm  
  
-   ExtraInfo: 「」\#contents  
  
 UrlPath のフィールドを処理するには \(たとえば、\) [GetUrlPath](../Topic/CUrl::GetUrlPath.md)、[GetUrlPathLength](../Topic/CUrl::GetUrlPathLength.md)と [SetUrlPath](../Topic/CUrl::SetUrlPath.md)を使用します。  完全な URL 文字列を作成するには、[CreateUrl](../Topic/CUrl::CreateUrl.md) を使用します。  
  
## 必要条件  
 **Header:** atlutil.h  
  
## 参照  
 [クラス](../../atl/reference/atl-classes.md)