<script lang="ts">
  import { ProjectCard } from '$lib';
	import { Anchor, Container, Box, Divider, Group, Stack, Text, ThemeIcon, Title, SimpleGrid } from '@svelteuidev/core';
	import type { Project } from '../app';
  import { AiFillGithub, AiFillLinkedin, AiFillMail } from "svelte-icons-pack/ai";
  import { Icon } from 'svelte-icons-pack';

  const projects: Project[] = [
    {
      title: 'Simple Real estate web',
      description: [
        'This project is a web application designed to showcase properties available for rent or sale, providing users with a detailed filtering system to easily find their desired properties. Each listing features comprehensive descriptions, images, and a contact form for inquiries.',
        'The platform also includes a secure admin portal where publishers can manage property listings, update or delete entries, and view user comments and inquiries. Built with Next.js for the frontend and PostgreSQL for the backend, this application ensures a seamless and efficient user experience, both for property seekers and publishers.',
      ],
      imageSrc: 'images/realestate-preview.webp',
      link: 'https://real-estate.androb.ar',
      githubLink: 'https://github.com/Androbar/real-estate-manager',
      technologies: ['React', 'Typescript', 'Next.js', 'Chakra ui', 'Postgres', 'Prisma', 'React hook forms', 'React Query']
    },
    {
      title: 'Private chat',
      description: [
        'This project is a simple and secure chat application where users can create chat rooms protected by passwords. Users can share the chat link and password with others, allowing them to join with their desired usernames. The application displays a list of online users and indicates who is currently typing, enhancing the chat experience.',
        'To manage online users, passwords, and messages, the application connects to a Redis database. The main technologies used in this project are Next.js for the frontend, Redis for the database, and Socket.IO for real-time communication.'
      ],
      imageSrc: 'images/private-chat.webp',
      link: 'https://private-chat.androb.ar',
      githubLink: 'https://github.com/Androbar/private-chat',
      technologies: ['React', 'Typescript', 'Next.js', 'Chakra Ui', 'Redis', 'Socket.io', 'Docker compose']
    },
    {
      title: 'Androb.ar',
      description: [
        'This project is a simple static page created with Svelte and SvelteUI, designed to showcase my various web development projects. The page provides a minimalistic interface to explore and learn more about each project, demonstrating my skills and interests in modern web technologies.'
      ],
      imageSrc: 'images/androbar.webp',
      link: 'https://androb.ar',
      githubLink: 'https://github.com/Androbar/androbar-page',
      technologies: ['Svelte', 'Typescript', 'SvelteUI']
    },
    {
      title: 'Clock overlay',
      description: [
        "The Overlay Clock App is a practical and customizable timekeeping tool that stays on top of all windows, ensuring you always have a clear view of the current time and date. Built with Svelte and Tauri, it allows you to personalize the clock's appearance by choosing from various fonts, background and font colors, and time and date formats. The clock can be easily hidden or shown using the Ctrl+Shift+H shortcut, making it a convenient addition to any desktop setup."
      ],
      imageSrc: 'images/clock-overlay-2.webp',
      githubLink: 'https://github.com/Androbar/overlay-clock',
      technologies: ['Svelte', 'Typescript', 'Tauri', 'Tailwind']
    }
  ];
</script>

<svelte:head>
  <title>Andob.ar</title>
</svelte:head>

<Box root="main">
  <Box root="section" css={{
    backgroundColor: "AliceBlue",
    color: "white",
    padding: "50px 20px",
    textAlign: "center",
  }}>
    <Container size={"xl"}>
      <Box css={{marginBottom: 16}}>
        <Title css={{marginBottom: 8}} order={1}>Andrés Arias</Title>
        <Text size="xl">Sr. Full Stack Software Engineer</Text>
        <Text size="lg">Based on Salta, Argentina</Text>
      </Box>
      <Stack gap="md">
        <Group>
          <ThemeIcon>
            <Icon src={AiFillMail} />
          </ThemeIcon>
          <Text>Mail: <Anchor href="mailto:andresrarias@gmail.com">andresrarias@gmail.com</Anchor></Text>
        </Group>
        <!-- <Group>
          <ThemeIcon>
            <Icon src={AiFillPhone} />
          </ThemeIcon>
          <Text>Phone number: <Anchor href="tel:+543876305969">+543876305969</Anchor></Text>
        </Group> -->
        <Group>
          <ThemeIcon>
            <Icon src={AiFillGithub} />
          </ThemeIcon>
          <Text>Main github account: <Anchor target="_blank" href="https://github.com/Androbas">https://github.com/Androbas</Anchor></Text>
        </Group>
        <Group>
          <ThemeIcon>
            <Icon src={AiFillGithub} />
          </ThemeIcon>
          <Text>Secondary github account: <Anchor target="_blank" href="https://github.com/Androbar">https://github.com/Androbar</Anchor></Text>
        </Group>
        <Group>
          <ThemeIcon>
            <Icon src={AiFillLinkedin} />
          </ThemeIcon>
          <Text><Anchor target="_blank" href="https://www.linkedin.com/in/andres-arias-754517177/">LinkedIn account</Anchor></Text>
        </Group>
      </Stack>
    </Container>
  </Box>

   <Box root="section" css={{ marginTop: "50px" }}>
    <Container size={"xl"}>
      <Stack gap={4}>
        <Text size="lg" css={{lineHeight: "1.4"}}>
          I'm a versatile full stack developer with over 5 years of experience in designing, developing, and managing complex software projects. My expertise spans across various technologies including Python, PostgreSQL, Javascript, ReactJS, and Next.js. I thrive in collaborative environments and take pride in delivering high-quality work that makes a lasting impact.
        </Text>
        <Text size="lg" css={{lineHeight: "1.4"}}>
          Most of my professional work is proprietary to my employers, so I am unable to showcase it here. However, I have created a few sample projects to demonstrate my skills and what I can bring to your team.
        </Text>
      </Stack>
    </Container>
  </Box>

  <Divider />

  <Box root="section" css={{ marginTop: "50px", marginBottom: "20px" }}>
    <Container size={"xl"}>
      <Title order={2}>Sample Projects</Title>
    </Container>
  </Box>

  <Box root="section">
    <Container size={"xl"}>
      <SimpleGrid
        cols={2}
        spacing={'md'}
        breakpoints={[{ maxWidth: 980, cols: 1}]}
      >
        {#each projects as project}
          <ProjectCard {project} />
        {/each}
      </SimpleGrid>
    </Container>
  </Box>
</Box>

