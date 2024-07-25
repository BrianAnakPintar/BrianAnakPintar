# Welcome.<img src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fblog-img.luanruisong.com%2Fblog%2Fimg%2F20210304140340.gif&f=1&nofb=1&ipt=3a11d4b86aded7bf3021370f80fc056e78d3e2521609d65478a30ce315e273f5&ipo=images" alt="Simple Images" title="Simple Image" width="70"/>

My name is Brian. I'm currently an Honours Computer Science student UBC. Here are some things I made:

- ⌨️ [My own text editor in C++](https://github.com/BrianAnakPintar/step-writer).
- 🏃 [An ice-breaker game where you run around inside a building competing for rooms](https://github.com/BrianAnakPintar/RoomRival).
- 🧑‍🏫 [A web app where you rate can review and rate your teachers](https://github.com/BrianAnakPintar/TARA).
- 🍣 [A rhythm sushi eating game](https://youtu.be/Gcul3Cpx8Pk).
- 📖 [My blog where I talk about things](https://www.brianmoniaga.com/Blog).

You can learn more about me in my site [here](https://brianmoniaga.com/)
If you are interested, you could also help me in improving my projects! I am currently looking to improve [step-writer](https://github.com/BrianAnakPintar/step-writer), if you are interested feel free to contribute!

This is my favorite sorting algorithm.
```go
func task(n int, result *[]int, wg *sync.WaitGroup, mx *sync.Mutex) {
  defer wg.Done()
  time.Sleep(time.Duration(n) * time.Millisecond)

  mx.Lock()
  *result = append(*result, n)
  mx.Unlock()
}

func sort(nums []int) []int {
  var wg sync.WaitGroup
  var mx sync.Mutex
  result := make([]int, 0, len(nums))

  for _, num := range nums {
    wg.Add(1)
    go task(num, &result, &wg, &mx)
  }

  wg.Wait()
  return result
}
```
