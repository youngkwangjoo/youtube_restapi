# youtube_restapi

### url : https://www.notion.so/docker_task-e72be885341447c68eceb6778cd2a052

### task2 url : https://www.notion.so/DJango-11-bdedfd321b784785b7cc2257284cb6c1

(1) User =>users
- email
- password
- nickname
- is_business

(2) Video videos
- title
- description
- link
- views_count
- thumbnail
- video_file: link
- User: FK

ex) 파일(이미지, 동영상)
=> 장고에 부하가 걸림.
=> S3 Bucket(저렴, 속도가 빠름) -> 결과물: 링크

(3) Reaction reactikons
- User: FK
- Video: FK
- reaction (like, dislike, cancel) => 실제 youtube rest api

(4) Comment
- User: FK
- Video: FK
- content
- like
- dislike

(5) Subscription => subscriptions
- User: FK => subscriber (내가 구독한 사람)
- User: FK => subscribed_to (나를 구독한 사람)

(6) Common
- created_at
- updated_at


users:
역할: 유튜브 사용자 정보를 관리.
세부 사항: 사용자 프로필, 인증 정보, 개인 설정 등을 포함. 또한 사용자가 업로드한 비디오와 남긴 댓글 등을 연관지을 수 있음.

videos:
역할: 유튜브 비디오 정보를 관리.
세부 사항: 비디오의 메타데이터(제목, 설명, 태그 등), 업로드된 파일, 재생 횟수, 좋아요 및 싫어요 수, 비디오의 소유자 정보 등을 포함.

reactions:
역할: 비디오에 대한 사용자 반응을 관리.
세부 사항: 좋아요, 싫어요, 기타 반응(예: 감정표현 이모티콘) 등을 기록. 어떤 사용자가 어떤 비디오에 어떤 반응을 보였는지 추적.

comments:
역할: 비디오에 대한 사용자 댓글을 관리.
세부 사항: 댓글 내용, 댓글 작성자, 작성 시간, 대댓글 구조, 좋아요 및 싫어요 수 등을 포함.

subscriptions:
역할: 사용자 구독 정보를 관리.
세부 사항: 사용자가 구독한 채널 목록, 구독 시작 및 종료 시점, 알림 설정 여부 등을 포함.

common:
역할: 공통적으로 사용되는 요소나 기능을 관리.
세부 사항: API 요청 및 응답 형식, 에러 처리, 공통적으로 필요한 유틸리티 함수, 데이터 변환 로직 등을 포함.