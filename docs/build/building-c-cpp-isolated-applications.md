---
title: "分離アプリケーションの C と C++ のビルド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: isolated applications [C++]
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5af0dde80a143166d9824d2739632ca7e7ed4382
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="building-cc-isolated-applications"></a>C/C++ 分離アプリケーションのビルド
分離アプリケーションでは、サイド バイ サイド アセンブリにのみ依存し、その依存関係が、マニフェストを使用してバインドします。 Windows 上で動作するために完全に分離するアプリケーションの必要はありません。ただし、アプリケーションを完全に分離に投資すること、可能性があります時間を節約してアプリケーションに将来のサービスを提供する必要がある場合。 アプリケーションを完全に分離の利点の詳細については、次を参照してください。[分離アプリケーション](http://msdn.microsoft.com/library/aa375190)です。  
  
 Visual C を使用してネイティブ C/C++ アプリケーションをビルドするときに既定では、Visual Studio プロジェクト システム マニフェスト ファイルを生成 Visual C ライブラリへのアプリケーションの依存関係について説明します。 これらは、唯一の依存関係、アプリケーションに場合、Visual Studio で、再構築は、独立したアプリケーションになります。 アプリケーションが実行時に、その他のライブラリを使用するかどうかに記載の手順に従って、サイド バイ サイド アセンブリとしてこれらのライブラリをリビルドする必要があります[C/C++ サイド バイ サイド アセンブリを構築する](../build/building-c-cpp-side-by-side-assemblies.md)です。  
  
## <a name="see-also"></a>関連項目  
 [分離アプリケーションとサイド バイ サイド アセンブリの概念](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [C/C++ 分離アプリケーションおよび side-by-side アセンブリのビルド](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)