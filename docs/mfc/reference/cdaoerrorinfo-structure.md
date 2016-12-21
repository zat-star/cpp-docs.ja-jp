---
title: "CDaoErrorInfo 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDaoErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoErrorInfo 構造体"
  - "DAO (データ アクセス オブジェクト), Errors コレクション"
ms.assetid: cd37ef71-b0b3-401d-bc2b-540c9147f532
caps.latest.revision: 13
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoErrorInfo 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CDaoErrorInfo` 構造体は、データ アクセス オブジェクト \(DAO\) に対して定義された Error オブジェクトに関する情報が含まれます。  
  
## 構文  
  
```  
  
      struct CDaoErrorInfo  
{  
   long m_lErrorCode;  
   CString m_strSource;  
   CString m_strDescription;  
   CString m_strHelpFile;  
   long m_lHelpContext;  
};  
```  
  
#### パラメーター  
 *m\_lErrorCode*  
 数値 DAO の場合はエラー コードを返します。  DAO ヘルプの「トラップできるなデータ アクセスのエラー」を参照してください。  
  
 *m\_strSource*  
 最初に、エラーを生成したアプリケーションまたはオブジェクトの名前。  ソース プロパティが最初にエラーを生成したオブジェクトを表す文字列式を指定します; 式は、通常、オブジェクトのクラスの名前です。  詳細については、" DAO ヘルプの「ソース プロパティ」を参照してください。  
  
 *m\_strDescription*  
 エラーに関連付けられたエラーを説明する文字列。  詳細については、" DAO ヘルプの「Description Property」を参照してください。  
  
 *m\_strHelpFile*  
 Microsoft Windows のヘルプ ファイルの絶対パス。  詳細については、「HelpContext の DAO ヘルプの HelpFile のプロパティ」を参照してください。  
  
 *m\_lHelpContext*  
 Microsoft Windows ヘルプ ファイルのトピックのコンテキスト ID。  詳細については、「HelpContext の DAO ヘルプの HelpFile のプロパティ」を参照してください。  
  
## 解説  
 MFC は DAO クラスの Error オブジェクトをカプセル化します。  代わりに、[CDaoException](../../mfc/reference/cdaoexception-class.md) クラスは DAO **DBEngine** オブジェクト、およびすべてのワークスペースを含むオブジェクトに含まれるエラー コレクションにアクセスするためのインターフェイスを提供します。  MFC DAO 操作がキャッチ `CDaoException` オブジェクトをスローする場合、MFC は `CDaoErrorInfo` 構造体を受け取り、例外オブジェクトの [m\_pErrorInfo](../Topic/CDaoException::m_pErrorInfo.md) のメンバーに格納されます。DAO を直接呼び出すことを選択した場合 `m_pErrorInfo`に合わせて独自の [GetErrorInfo](../Topic/CDaoException::GetErrorInfo.md) 例外オブジェクトのメンバー関数を呼び出す必要があります。  
  
 DAO のエラーの処理に関する詳細については、記事 [例外: データベースの例外](../../mfc/exceptions-database-exceptions.md)を参照します。  関連情報については、" DAO ヘルプの「Error オブジェクト」を参照してください。  
  
 [CDaoException::GetErrorInfo](../Topic/CDaoException::GetErrorInfo.md) のメンバー関数によって取得される情報は `CDaoErrorInfo` 構造に格納されます。  、例外ハンドラーでキャッチ、または DAO に直接呼び出し中に発生する可能性のあるエラーをチェックするように明示的に作成する `CDaoException` オブジェクトからの呼び出し `GetErrorInfo` はインターフェイス。`CDaoException` オブジェクトから [m\_pErrorInfo](../Topic/CDaoException::m_pErrorInfo.md) のデータ メンバーを確認します。  `CDaoErrorInfo` は、デバッグ ビルドの `Dump` のメンバー関数を定義します。  `CDaoErrorInfo` オブジェクトの内容をダンプするために `Dump` を使用できます。  
  
## 必要条件  
 **ヘッダー:** afxdao.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoException クラス](../../mfc/reference/cdaoexception-class.md)