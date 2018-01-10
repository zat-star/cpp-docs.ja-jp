---
title: "Windows ランタイムのサポートされていない CRT 関数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- unsupported CRT functions, Windows Runtime
- Windows Runtime, unsupported CRT functions
ms.assetid: bb8386d6-0ef8-460c-88d8-addff009b6f1
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d3e5e2f8ffab670c6e6c5eb95d37b4daced5c6b3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="windows-runtime-unsupported-crt-functions"></a>Windows ランタイムのサポートされていない CRT 関数
多くの C ランタイム (CRT) API は、Windows ランタイムで実行する [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリでは使用できません。 これらのアプリは /ZW コンパイラ フラグを使用してビルドします。 サポートされない CRT 関数の一覧については、「[/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
 すべての CRT API については、このドキュメントの「[関数リファレンス (アルファベット順)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)」のセクションを参照してください。  
  
## <a name="see-also"></a>参照  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)   
 [関数リファレンス (アルファベット順)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)