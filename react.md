# React & Redux Developer Practice

## File Structure
- Use **camelCase** for naming convention of folders.
- Add local components inside the **src/Components/{stakeholderName/Process}**
- Add global components inside the **src/components-new/GlobalComponents**
- Add pages inside the **src/Pages/{stakeholderName/Process}**
- If the screen is used multiple times in other stakeholders add a url parameter to make it dynamic.

## Naming Convention

### Component & Page Naming Convention
- Always use **camelCase** for naming convention.
- Follow the naming convention of the component from figma.

### RouteNaming Convention
- Always use **kebab-case** for route convention.
- Stakeholder specific route structure should be followed `/{stakeholder}/page-name`
- Gloval route structure should be followed `/page-name`
- Always use optional parameters to make url dynamic.
- Optional parameters should be at the end of the url and should not be considered as part of the url while following route naming convension.

### Redux Naming Convention
- Always use **camelCase** for redux convention.
- Always use `reducer` at the end of reducer function name.
- Always use `action` at the end of action function name.
- Always use `Slice` at the end of the slice name.

## Component Design
- Always define type for the props of the component.
- Never add any static value to the component.
- **Don't write plain css** for the components use a `styled component` or `tailwind css` or define css using `React.CssProperties`. _(Plain css can improve performance but it is a mess to scale it with multiple components and it is not a good practice)_
- Don't ever break a previously made component. If you want to modify the previously required prop of that component for your usecases, then defind the type of the variable and add the previously passed data as the default value and also if you are adding new props then make those optioonal so that those component don't break if they don't pass.
- If you still need to change any previous type contact the person who created the component and discuss and make changes according to discusssion.
- Once the component , add a little documentation of **How to use it?** 

## Writing Test
- Write tests for each component and page while development.
- Follow TDD.
- If you don't know how to write test. Lean it from the below youtube link.
- [https://youtu.be/T2sv8jXoP4s?si=y_36-4PSH__1cRbZ](https://youtu.be/T2sv8jXoP4s?si=y_36-4PSH__1cRbZ)

## Coding Patterns to Follow
- Always use **arrow functions** as we are using functional component. 
- Use `useMemmo` for performance improvement to prevent from unnecessary re-rendering.
- Use `useSelector` and `useDispatch` to get access to state and dispatch data.
- Don't make api calls without redux action.
- Use `useEffect` with passing an empty array to perform any action during the component mount.
  Example: 
  ```js
    useEffect(() => { 
        // necessary actions
    }, [])
  ```
- If it is not a static link, then always use `useNavigate` to programmatically navigate.
- Always use `AxiosInstance` to make api calls.
