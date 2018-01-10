---
title: "以前のオペレーティング システムにおける CImage の制限 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CImage
dev_langs: C++
helpviewer_keywords: CImage class [MFC], limitations
ms.assetid: 4bedaab8-7dd1-4c91-ab35-b75fb56765b0
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 27046704975bf8f5e28f12acbfa72e860660fdbd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cimage-limitations-with-earlier-operating-systems"></a>以前のオペレーティング システムにおける CImage の制限
多く`CImage`関数は、新しいバージョンの Windows でのみ動作します。 Windows 95/98 または Windows NT 4.0 および Windows 2000 です。 この記事では、特定のメソッドのバージョンの制限事項について説明します。  
  
 [CImage::PlgBlt](../atl-mfc-shared/reference/cimage-class.md#plgblt)と[CImage::MaskBlt](../atl-mfc-shared/reference/cimage-class.md#maskblt) Windows NT 4.0 のみで機能またはそれ以降。 Windows 95/98 以降を実行しているアプリケーションでは機能しません。  
  
 [CImage::AlphaBlend](../atl-mfc-shared/reference/cimage-class.md#alphablend)と[CImage::TransparentBlt](../atl-mfc-shared/reference/cimage-class.md#transparentblt)唯一の Windows 2000 以降と Windows 98 以降ため、これらのメソッドを使用する msimg32.lib とリンクする必要があります。 (このライブラリは Windows 2000 以降と Windows 98 を実行するアプリケーションにのみ使用可能なまたはそれ以降) です。  
  
 含めることができます`AlphaBlend`と`TransparentBlt`これらのメソッドを取得呼び出されない場合にのみ、Windows 95 または Windows NT 4.0 で実行されているアプリケーションでします。 場合は、アプリケーションには、これらのメソッドが含まれています。 以前のオペレーティング システムで実行する必要がありますが、リンカーのに使用する必要があります[/delayload](../build/reference/delayload-delay-load-import.md) msimg32.lib の読み込みを遅延します。 アプリケーションが Windows NT 4.0 または Windows 95 で実行中にこれらのメソッドのいずれかにも呼び出さない限り msimg32.lib を読み込むことはしません。 かどうかを確認することができますの透過性のサポートは、使用可能なを使用して、`CImage::IsTransparencySupported`メソッドです。  
  
## <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocViewSDI#8](../mfc/codesnippet/cpp/cimage-limitations-with-earlier-operating-systems_1.cpp)]  
  
 これらのメソッドを呼び出すアプリケーションをコンパイルするには、挿入、#define する前に _WIN32_WINNT ステートメント # Windows のバージョンが 5.0 以上であることを示す、システム ヘッダーを including:  
  
 [!code-cpp[NVC_MFCDocViewSDI#9](../mfc/codesnippet/cpp/cimage-limitations-with-earlier-operating-systems_2.h)]  
  
 使用せず msimg32.lib に直接リンクすることができる場合は、アプリケーションは、Windows 2000 または Windows 98 よりも古いオペレーティング システムで実行する必要はありません、 **/delayload**です。  
  
 [:Draw](../atl-mfc-shared/reference/cimage-class.md#draw) Windows NT 4.0 または Windows 95 ではよりも、Windows 2000 および Windows 98 で使用する場合とは異なる動作です。  
  
 0x0500 より小さい値に _WIN32_WINNT セットでアプリケーションをコンパイルする場合**描画**は、作業が処理せず 98 以降、Windows 2000 および Windows を実行しているシステムに自動的に透明度。  
  
 _WIN32_WINNT 0x0500 に設定とアプリケーションまたはそれ以上をコンパイルする場合**描画**98 以降、Windows 2000 または Windows を実行しているシステムに自動的に透過性を処理します。 動作もせずに Windows NT 4.0、Windows 95; での透過性のサポートただし、使用する必要があります**/delayload** msimg32 の読み込みを遅延します。LIB、前述の`AlphaBlend`と`TransparentBlt`です。  
  
## <a name="see-also"></a>参照  
 [CImage クラス](../atl-mfc-shared/reference/cimage-class.md)
