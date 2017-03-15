---
title: "ATL OLE DB プロバイダー ウィザード | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.provider.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL OLE DB プロバイダー ウィザード"
  - "ATL プロジェクト, 追加 (ATL OLE DB プロバイダーを)"
ms.assetid: cf91ba78-01d1-4d12-b673-e95d96bfbebe
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# ATL OLE DB プロバイダー ウィザード
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このウィザードでは、OLE DB プロバイダーを構成するクラスを作成します。  
  
## 解説  
 [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)] から、このウィザードによって生成される登録スクリプトでは、COM コンポーネントは **HKEY\_LOCAL\_MACHINE** ではなく、**HKEY\_CURRENT\_USER** に登録されるようになりました。  この動作を変更するには、ATL ウィザードの **\[すべてのユーザーについてコンポーネントを登録\]** オプションをオンにします。  
  
 ATL OLE DB プロバイダー ウィザードのオプションを次の表に示します。  
  
 **\[短い名前\]**  
 作成されるプロバイダーの短い形式の名前を入力します。  入力された名前に基づいて、ウィザードの別のエディット ボックスも自動的に変更されます。  必要に応じて、他の名前ボックスを編集できます。  
  
 **\[CoClass\]**  
 コクラスの名前。  ProgID 名を変更してこの名前と一致させます。  
  
 **\[属性付き\]**  
 このオプションでは、ウィザードがプロバイダー クラスを作成するときに属性とテンプレート宣言のどちらを使用するかを指定します。  このオプションを選択すると、ウィザードはテンプレート宣言ではなく属性を使用します。これは、属性付きプロジェクトを作成した場合の既定のオプションです。  このオプションの選択を解除すると、ウィザードは属性ではなくテンプレート宣言を使用します。これは、属性なしプロジェクトを作成した場合の既定のオプションです。  
  
 属性なしプロジェクトを作成したときにこのオプションを選択すると、現在のプロジェクトが属性付きプロジェクトに変換されるというメッセージが表示され、操作を継続するかどうかを確認されます。  
  
 **\[ProgID\]**  
 ProgID \(プログラム ID\) とは、GUID の代わりにアプリケーションで使用できるテキスト文字列です。  ProgID 名の形式は *Projectname*.*Coclassname* です。  
  
 **Version**  
 プロバイダーのバージョン番号です。  既定値は 1 です。  
  
 **\[データソース クラス\]**  
 データ ソース クラスの名前。形式は C`Shortname`Source です。  
  
 **\[データソース .h ファイル\]**  
 データ ソース クラスのヘッダー ファイルです。  ファイルの名前を変更することも、現存のヘッダー ファイルを選択することもできます。  
  
 **\[セッション\]**  
 セッション クラスの名前。形式は C`Shortname`Session です。  
  
 **\[セッション .h ファイル\]**  
 セッション クラスのヘッダー ファイルです。  ファイルの名前を変更することも、現存のヘッダー ファイルを選択することもできます。  
  
 **\[コマンド クラス\]**  
 コマンド クラスの名前。形式は C`Shortname`Command です。  
  
 **\[コマンド .h ファイル\]**  
 コマンド クラス用のヘッダー ファイル。  この名前は編集できません。行セット ヘッダー ファイルの名前に基づいて決まります。  
  
 **\[行セット クラス\]**  
 行セット クラスの名前。形式は C`Shortname`Rowset です。  
  
 **\[行セット .h ファイル\]**  
 行セット クラスのヘッダー ファイルです。  ファイルの名前を変更することも、現存のヘッダー ファイルを選択することもできます。  
  
 **\[行セット .cpp ファイル\]**  
 プロバイダーの実装ファイルです。  ファイルの名前を変更することも、現存の実装ファイルを選択することもできます。  
  
## 参照  
 [ATL OLE DB Provider](../../atl/reference/adding-an-atl-ole-db-provider.md)