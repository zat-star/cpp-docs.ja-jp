---
title: "使用するアクセサーの種類の決定 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アクセサー [C++], 種類"
  - "行セット [C++], データ型"
ms.assetid: 22483dd2-f4e0-4dcb-8e4d-cd43a9c1a3db
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 使用するアクセサーの種類の決定
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

行セットのデータ型は、コンパイル時または実行時に決定できます。  
  
 コンパイル時にデータ型を決定する必要がある場合は、静的アクセサー \(`CAccessor` など\) を使用します。  データ型は、手動で決定することも、ATL OLE DB コンシューマー ウィザードを使用して決定することもできます。  
  
 実行時にデータ型を決定する必要がある場合は、動的アクセサー \(`CDynamicAccessor` またはその子\) または手動アクセサー \(`CManualAccessor`\) を使用します。  この場合は、行セットに対して `GetColumnInfo` を呼び出して、列の連結の情報を返すことができます。この情報から型を決定できます。  
  
 次の表は、コンシューマー テンプレートで提供されるアクセサーの種類の一覧を示します。  各アクセサーには長所と短所があります。  状況に応じて、使用に適したアクセサーの種類があります。  
  
|アクセサー クラス|バインディング|パラメーター|コメント|  
|---------------|-------------|------------|----------|  
|`CAccessor`|`COLUMN_ENTRY` マクロを使用してユーザー レコードを作成します。  マクロは、そのレコードのデータ メンバーをアクセサーに連結します。  行セットが作成されると、列のバインドは解除できません。|適用あり。**PARAM\_MAP** マクロ エントリを使用します。  連結された後は、パラメーターの連結を解除できません。|コード量が少ないため、最も高速なアクセサーです。|  
|`CDynamicAccessor`|自動。|できません。|行セットのデータ型が不明な場合に役立ちます。|  
|`CDynamicParameterAccessor`|自動ですが、[オーバーライド](../../data/oledb/overriding-a-dynamic-accessor.md)できます。|適用あり。ただし、プロバイダーが `ICommandWithParameters` をサポートしている場合です。  パラメーターは自動的に連結されます。|`CDynamicAccessor` より低速ですが、汎用ストアド プロシージャの呼び出しには便利です。|  
|**CDynamicStringAccessor\[A,W\]**|自動。|できません。|アクセスされるデータをデータ ストアから文字列データとして取得します。|  
|`CManualAccessor`|`AddBindEntry` を使用して手動で行います。|`AddParameterEntry` を使用して手動で指定します。|処理が高速です。パラメーターと列は 1 回だけ連結されます。  ユーザーが使用するデータ型を決定します。例については、[DBVIEWER](http://msdn.microsoft.com/ja-jp/07620f99-c347-4d09-9ebc-2459e8049832) のサンプルを参照してください。`CDynamicAccessor` または `CAccessor` のほかにコードが必要です。  これは OLE DB の直接呼び出しに似ています。|  
|`CXMLAccessor`|自動。|できません。|アクセスされるデータをデータ ストアから文字列データとして取得し、XML タグ付きデータとして書式設定します。|  
  
## 参照  
 [アクセサーの使用](../../data/oledb/using-accessors.md)