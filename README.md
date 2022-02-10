# React Hook Debouncing

## Installation

```sh
npm install @devarista/react-debounce
```

## Usage

To start using the `useDebounce()` hook, please follow these steps:

1. Import the npm package to your components or pages.

    ```javascript
    import { useDebounce } from '@devarista/react-debounce'
    ```

2. Call the hook inside your Function.

    Required two parameters `value:any, delay:number`. You can give any value to `value` parameter, and number to `delay` parameter.
    `delay` _parameter equal to miliseconds._

    ```javascript
    const Home = ({images}) => {
        const [imageData, setImageData] = useState(props.images)
        const [tags, setTags] = useState(null)
    
        const debouncedSearch = useDebounce(tags, 500)
    
        useEffect(() => {
            const getImagesWithTags = async () => {
                const { data } = await axios.get(`${process.env.NEXT_PUBLIC_SERVER_URL}/image?tags=${debouncedSearch}`)
                return setImageData(data)
            }

            getImagesWithTags()
        }, [debouncedSearch])
    
        return (
            <div>
                ...
            </div>
        )
    }
    ```

## Examples

- GitHub Repo (Next.js) : <https://github.com/devarista/flickr-gallery-frontend>
- Codesandbox : <https://github.com/devarista>

## Contributing

Feel like contributing? That's awesome!. Fork me and make a pull request.
