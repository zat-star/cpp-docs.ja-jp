---
title: "OLE DB プロバイダーへの文字列の格納 | Microsoft Docs"
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
  - "ユーザー レコード, 編集"
ms.assetid: 36cb9635-067c-4cad-8f85-962f28026f6a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE DB プロバイダーへの文字列の格納
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL OLE DB プロバイダー ウィザードでは、MyProviderRS.h に `CWindowsFile` という既定のユーザー レコードが作成されます。  2 つの文字列を処理するには、`CWindowsFile` を変更するか、次のコードに示すように独自のユーザー レコードを追加します。  
  
```  
////////////////////////////////////////////////////////////////////////  
class CAgentMan:   
   public WIN32_FIND_DATA  
   DWORD dwBookmark;              // Add this  
   TCHAR szCommand[256];          // Add this  
   TCHAR szText[256];             // Add this  
   TCHAR szCommand2[256];         // Add this  
   TCHAR szText2[256];            // Add this  
  
{  
public:  
BEGIN_PROVIDER_COLUMN_MAP()  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Command"), 1, 256, GUID_NULL, CAgentMan, szCommand)  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Text"), 2, 256, GUID_NULL, CAgentMan, szText)   
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Command2"), 3, 256, GUID_NULL, CAgentMan, szCommand2)  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Text2"),4, 256, GUID_NULL, CAgentMan, szText2)  
END_PROVIDER_COLUMN_MAP()  
   bool operator==(const CAgentMan& am) // This is optional   
   {  
      return (lstrcmpi(cFileName, wf.cFileName) == 0);  
   }  
};  
```  
  
 データ メンバー `szCommand` と `szText` は、2 つの文字列を表します。必要に応じて、`szCommand2` と `szText2` で追加の列を用意します。  `dwBookmark` データ メンバーは、この単純な読み取り専用プロバイダーには不要ですが、後で `IRowsetLocate` インターフェイスを追加する際に使用します。「[単純な読み取り専用プロバイダーの機能の拡張](../../data/oledb/enhancing-the-simple-read-only-provider.md)」を参照してください。  `==` 演算子はインスタンスを比較します。この演算子の実装は省略できます。  
  
 この処理が終了すると、プロバイダーはいつでもコンパイルして実行できます。  プロバイダーをテストするには、対応する機能を持つコンシューマーが必要です。  「[単純なコンシューマーの実装](../../data/oledb/implementing-a-simple-consumer.md)」に、このようなテスト コンシューマーの作成方法を示します。  テスト コンシューマーをプロバイダーと共に実行します。  \[テスト コンシューマー\] ダイアログ ボックスの \[実行\] ボタンをクリックしたときに、テスト コンシューマーが適切な文字列をプロバイダーから取得することを確認します。  
  
 プロバイダーのテストが正常に終了すると、追加のインターフェイスを実装することにより、プロバイダーの機能を拡張できます。  「[単純な読み取り専用プロバイダーの機能の拡張](../../data/oledb/enhancing-the-simple-read-only-provider.md)」で例を示します。  
  
## 参照  
 [単純な読み取り専用プロバイダーの実装](../../data/oledb/implementing-the-simple-read-only-provider.md)