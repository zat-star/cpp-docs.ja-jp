---
title: "インポート ライブラリとエクスポート ファイルの操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- LIB [C++], /DEF option
- import libraries
- LIB [C++], import libraries and export files
- export files
- import libraries, creating
ms.assetid: d8175596-9773-4c2f-959d-b05b065a5161
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9e0d60eed00abc60c09e03838a113c424d8f173a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="working-with-import-libraries-and-export-files"></a>インポート ライブラリとエクスポート ファイル
/DEF オプションを使用して LIB を使用して、インポート ライブラリとエクスポート ファイルを作成することができます。 リンクの使用を含むプログラムをビルドするファイルのエクスポートが (通常、ダイナミック リンク ライブラリ (DLL)) をエクスポートし、他のプログラムでこれらのエクスポートへの参照を解決するのには、インポート ライブラリを使用します。  
  
 .Dll を作成する前に、準備手順で、インポート ライブラリを作成する場合を渡す必要がある同じ一連のオブジェクト ファイル、.dll を構築するときにインポート ライブラリを構築するときに渡したものとに注意してください。  
  
 ほとんどの状況では LIB を使用して、インポート ライブラリを作成する必要はありません。 エクスポートを含むプログラム (実行可能ファイルまたは DLL) をリンクするときのリンクは自動的にエクスポートを記述したインポート ライブラリを作成します。 後で、これらのエクスポートを参照しているプログラムをリンクする場合は、インポート ライブラリを指定します。  
  
 ただし、DLL のエクスポートからもインポートするプログラムをかどうか直接的または間接的に行う必要があります LIB インポート ライブラリのいずれかを作成します。 LIB は、インポート ライブラリを作成するときも、エクスポート ファイルを作成します。 Dll のいずれかをリンクするときに、エクスポート ファイルを使用する必要があります。  
  
## <a name="see-also"></a>参照  
 [LIB リファレンス](../../build/reference/lib-reference.md)