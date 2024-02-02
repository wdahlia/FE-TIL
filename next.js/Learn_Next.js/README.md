/* 모든 라우트에 걸친, 즉 어플리케이션 전반에 적용하기 위한 css 룰을 작성하는 공간 - css reset rule과 HTML elements에 대한 스타일링 */
/* global.css를 가장 root layer인, Layout.tsx에 위치 시키면, css가 적용됨 => 이유는 @tailwind ~; 때문 */
/* tailwindcss를 사용하면 라이브러리 내부에 기본 내장 되어있는 스타일링을 사용하여 className="" 내부에 간편하게 스타일 적용 할 수 있음 */
/* 각각의 element에 직접 적용하는 것이기 때문에, 스타일 충돌과, 스타일 시트의 분리, css 번들 사이즈를 고려할 필요성이 사라짐 */


import { ReactNode } from 'react';
import '@/app/ui/global.css';
