# 하늘을 나는 BaseMan
## player code
``` C#
int hp = 1; //hp를 1로 설정
public Text myhp; //남은 hp를 표시
public Text uText; //게임 종료, 게임 클리어 글자 표시
public float speed = 3; //플레이어 속도
public float speedUp = 0; //속도++
public GameObject Objects; //파티클 받아오기
Vector3 position;
// Start is called before the first frame update
void Start()
{
    Objects.SetActive(false); //파티클을 끈다
    position = transform.position; //지정
}

void speedup()
{
    speed += speedUp; // 갈 수록 빠르게
}
// Update is called once per frame
void Update()
{   
    Invoke("speedup", 1.0f); //속도 증가
    myhp.text = "BaseMan이 한 번 부딪히면 죽습니다"; //텍스트 표시
    position.z -= speed * Time.deltaTime; //앞으로 이동
    transform.position = position;
    Vector3 vec = new Vector3(
            Input.GetAxisRaw("Horizontal") * 4, 0, 0 //좌우 방향 이동
        );
    transform.Translate(vec);
}
void OnTriggerEnter(Collider other)
{
    if (other.gameObject.tag == "zombie") //좀비에 닿으면 실행
    {
        hp--;
        if (hp < 1)
        {
            uText.text = "GameOver R을 눌러 재시작";
            Objects.SetActive(true); //파티클 표시
            Destroy(gameObject); //플레이어 삭제
        }
    }
    if (other.gameObject.tag == "block") //block에 닿으면 실행
    {
        uText.text = "GameClear"; // 게임 클리어
        Destroy(gameObject); //플레이어 삭제
    }
}
```
## camera code
``` C#
public Transform target; //타겟 지정
public Vector3 offset;
void Update()
{
    transform.position = target.position + offset; //플레이어 따라가서 시점을 맞춰줌
}
```
## creat zombie code
``` C#
//랜덤으로 좀비를 생성하는 코드
public GameObject zombie; //좀비 프리펩 설정 도구
public GameObject rangeObject;
BoxCollider rangeCollider;
// Start is called before the first frame update
private void Awake()
{
    rangeCollider = rangeObject.GetComponent<BoxCollider>();
}
Vector3 Return_RandomPosition()
{
    Vector3 originPosigion = rangeObject.transform.position;
    float range_X = rangeCollider.bounds.size.x;
    float range_Z = rangeCollider.bounds.size.z;

    range_X = Random.Range((range_X / 2) * -1, range_X / 2);
    range_Z = Random.Range((range_Z / 2) * -1, range_Z / 2);
    Vector3 RandomPosition = new Vector3(range_X, 0f, range_Z);

    Vector3 respawnPosigion = originPosigion + RandomPosition;
    return respawnPosigion;
}
void Start()
{
    StartCoroutine(RandomRespawn_Coroutine());
}
IEnumerator RandomRespawn_Coroutine()
{
    while (true)
    {
        yield return new WaitForSeconds(0.5f); 
        GameObject instantCapsul = Instantiate(capsul, Return_RandomPosition(), Quaternion.identity);
    }
}
// Update is called once per frame
void Update()
{
    if (Input.GetKeyDown(KeyCode.R)) //R을 눌렀을시 재시작
    {
        SceneManager.LoadScene("SampleScene");
    }
}
```
## rotation code
``` C#
// 플레이어의 상위에 오브젝트를 만들어 돌아가게 했다
public Transform target; //타겟 설정
public Vector3 offset;
void Update()
{
    transform.position = target.position + offset; //위치 설정
    if (Input.GetAxisRaw("Horizontal") == 1)
    {
        transform.rotation = Quaternion.Euler(0, 0, -30); //오른쪽 키 클릭시 z축으로 -30도 돌리기
    }
    else if (Input.GetAxisRaw("Horizontal") == -1)
    {
        transform.rotation = Quaternion.Euler(0, 0, 30); //왼쪽 키 클릭시 z축으로 30도 돌리기
    }
    else
    {
        transform.rotation = Quaternion.Euler(0, 0, 0); // 아무 키도 안눌렀을 때 기울기 0
    }
}
```
## zombie code
``` C#
// zombie가 앞으로 달려가게 하는 코드 입니다 (player code중 일부를 수정)
Vector3 position;
// Start is called before the first frame update
void Start()
{
    position = transform.position;
}
// Update is called once per frame
void Update()
{
    position.z += 20 * Time.deltaTime;
    transform.position = position;
}
```