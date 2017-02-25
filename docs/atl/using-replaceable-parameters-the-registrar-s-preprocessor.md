---
title: "置き換え可能パラメーター (レジストラーのプリプロセッサ) の使用 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "AddReplacement"
  - "ClearReplacements"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "%MODULE%"
ms.assetid: 0b376994-84a6-4967-8d97-8c01dfc94efe
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 置き換え可能パラメーター (レジストラーのプリプロセッサ) の使用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

置き換え可能パラメーターは、レジストラー クライアントがランタイムのデータを指定することができます。  これを行うには、レジストラーは、スクリプトの置き換え可能パラメーターに関連付けられた値を入力する置換マップを保持します。  レジストラーは実行時に入力を行います。  
  
##  <a name="_atl_using_.25.module.25"></a> を使用して %MODULE%  
 [&#91;ATL コントロール ウィザード&#93;](../atl/reference/atl-control-wizard.md) が自動的に `%MODULE%`を使用するスクリプトを生成します。  ATL は、サーバー上の DLL または EXE の実際の場所でこの置き換え可能パラメーターを使用します。  
  
## スクリプトのデータの実行時のデータのバインド  
 プリプロセッサのもう一つの使用は、スクリプトのデータのランタイム データを連結することです。  たとえば、最後に追加した文字列「`, 1`」が付いているモジュールの完全パスを含む。エントリが必要であるとします。  最初に、次の拡張を定義する:  
  
```  
'MySampleKey' = s '%MODULE%, 1'  
```  
  
 次に、[スクリプトの開始](../atl/invoking-scripts.md)に示すメソッドを処理するスクリプトの 1 つがを呼び出す前に置換をマップに追加します:  
  
 [!CODE [NVC_ATL_Utilities#113](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#113)]  
  
 スクリプトの解析中、レジストラーは `c:\mycode\mydll.dll, 1`に `'%MODULE%, 1'` を展開します。  
  
> [!NOTE]
>  レジストラー スクリプトでは、KB は、最大のトークンのサイズです。   \(トークンは、構文を認識可能な要素です。これは、プリプロセッサによって作成された、または配置されたトークンが含まれています。  
  
> [!NOTE]
>  実行時に置換値を代入するには、[DECLARE\_REGISTRY\_RESOURCE](../Topic/DECLARE_REGISTRY_RESOURCE.md) または [DECLARE\_REGISTRY\_RESOURCEID](../Topic/DECLARE_REGISTRY_RESOURCEID.md) のマクロにスクリプトの呼び出しを削除します。  代わりに、メソッドを [CAtlModule::UpdateRegistryFromResourceD](../Topic/CAtlModule::UpdateRegistryFromResourceD.md) か [CAtlModule::UpdateRegistryFromResourceS](../Topic/CAtlModule::UpdateRegistryFromResourceS.md)を呼び出す置き換え、**\_ATL\_REGMAP\_ENTRY** の構造体の配列を渡す。`UpdateRegistry` に独自のメソッドで。  **\_ATL\_REGMAP\_ENTRY** の配列は、{、}**NULLNULL**設定されていると、このエントリは常に最後のエントリです。1 文字以上のエントリが必要です。  それ以外の場合は、アクセス違反のエラーが **UpdateRegistryFromResource** が呼び出された場合に生成されます。  
  
> [!NOTE]
>  プロジェクトをビルドしたときに出力が **%MODULE%** レジストラー スクリプト パラメーターの実行時に作成されるパス名の前後に実行可能ファイル、ATL 自動的に引用符を追加する。  パス名に引用符がしない場合 **%MODULE\_RAW%** に新しいパラメーターを使用します。  
>   
>  **%MODULE%** か **%MODULE\_RAW%** が使用されている場合は出力パス名が、ATL DLL に引用符を追加しないプロジェクトをビルドするとき。  
  
## 参照  
 [レジストラー スクリプトの作成](../Topic/Creating%20Registrar%20Scripts.md)