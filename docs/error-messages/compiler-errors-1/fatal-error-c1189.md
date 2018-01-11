---
title: "致命的なエラー C1189 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1189
dev_langs: C++
helpviewer_keywords: C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2330d49f817012fc2e0381a0991f709ada74ea32
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1189"></a>致命的なエラー C1189
\#エラー: ユーザーが指定したエラー メッセージ  
  
 C1189 がによって生成された、`#error`ディレクティブです。 ディレクティブをコード開発者は、エラー メッセージのテキストを指定します。 詳細については、次を参照してください。 [#error ディレクティブ (c/c++)](../../preprocessor/hash-error-directive-c-cpp.md)です。  
  
 次の例では、C1189 を生成します。 サンプルでは、開発者がカスタム エラー メッセージを発行、`_WIN32`識別子が定義されていません。  
  
```  
// C1189.cpp  
#undef _WIN32  
#if !defined(_WIN32)  
#error _WIN32 must be defined   // C1189  
#endif  
```  
  
 使用して ATL プロジェクトをビルドする場合にもこのエラーが発生する可能性があります、 **/robust** MIDL コンパイラ オプション。 使用して、 **/robust**ビルドのみへの切り替え[!INCLUDE[win2kfamily](../../c-runtime-library/includes/win2kfamily_md.md)]およびそれ以降のバージョンの Windows です。 このエラーを解決するには、次の手順のいずれかを使用します。  
  
-   この行 dlldatax.c ファイルに変更します。  
  
```  
#define _WIN32_WINNT 0x0400   // for WinNT 4.0 or Windows 95 with DCOM  
```  
  
 この行を次のように変更します。  
  
```  
#define _WIN32_WINNT 0x0500   // for WinNT 4.0 or Windows 95 with DCOM  
```  
  
-   使用して、 **詳細設定**プロパティ ページで、 **MIDL**プロパティ ページ フォルダーを削除する、 **/robust**を指定し、 **/no_robust**スイッチです。 詳細については、次を参照してください。 [midl プロパティ ページ: 高度な](../../ide/midl-property-pages-advanced.md)します。  
  
## <a name="see-also"></a>参照  
 [#define ディレクティブ (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)