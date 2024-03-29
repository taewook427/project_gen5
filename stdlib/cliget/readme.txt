stdlib5.cliget [win & linux] : CLI 환경에서의 파일/폴더 선택창 구현.

<go>
func Initget(str[] names, str[] paths) -> toolbox
# 바로가기 경로를 설정한 toolbox 구조체 생성.
struct toolbox
    func Getfile(str start) -> str
    # 시작할 폴더를 경로로 입력하고 파일 하나를 선택함.
    func Getfolder(str start) -> str
    # 시작할 폴더를 경로로 입력하고 폴더 하나를 선택함.

! 명령어 설명 !
바로가기(tp N) : tp와 숫자를 써서 바로가기 폴더로 현재 작업 폴더를 이동합니다.
이동(N) : 상위/하위 폴더로 이동합니다. 파일 선택인 경우 파일에 해당하는 숫자라면 파일이 선택됩니다.
선택(sel N) : 파일 또는 폴더를 선택합니다.
확장자 설정(only S) : 특정 확장자인 파일만 보여줍니다. 기본은 전체 모드인 "*"입니다.
직접입력(S) : 목표 경로를 문자열 그 자체로 직접 입력합니다.

CLI 환경에서 파일/폴더 선택을 더 쉽고 직관적으로 하기 위해 제작되었습니다.
기본적으로 폴더와 파일을 숫자로 나타내며, 입력에 간단한 명령과 숫자만 사용합니다.
폴더 목록의 0번째 항목은 "../"로, 상위 폴더를 나타냅니다.
only 명령어 사용 후 다시 모든 파일을 인식하려면 "only *"를 사용합니다.
only 명령은 폴더 선택 모드에서는 해당 문자열을 포함한 폴더만 표시되도록 하는 기능으로 바뀝니다.
직접입력 시 존재하는 경로라면 입력값 그 자체가 인식되며, "\"경로\"" 형식도 사용 가능합니다.
