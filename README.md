# react-i18n

A super-simple i18n solution for React app.

## Usage

### step 0: Define dictionary

i18n.json

```json
{
	"nav": {
		"homePage": {
			"zh-CN": "博客",
			"en-US": "Home"
		},
		"secondPage": {
			"zh-CN": "寂静地",
			"en-US": "Special"
		},
		"search": {}
	}
}
```

### step 1: Use

```tsx
import Text from "../../utils/i18n";
import { nav } from "../../data/i18n.json";

const Menu = ({ lang }): React.ReactElement => {
	return (
		<ul className="app-header-list">
			<Text dictionary={nav} language={lang}>
				{[
					{
						text: <Text homePage />,
						to: "/",
					},
					{
						text: <Text secondPage />,
						to: "/special",
					},
				].map((item, i) => (
					<ActiveLink
						activeClassName="app-header-list-item-active"
						href={item.to}
					>
						<a className="app-header-list-item">{item.text}</a>
					</ActiveLink>
				))}
			</Text>
		</ul>
	);
};
```

## LICENSE

MIT
